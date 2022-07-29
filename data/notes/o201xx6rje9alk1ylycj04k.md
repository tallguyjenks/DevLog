

```sql
CREATE OR REPLACE FUNCTION rpt.FN_Clean_Data() RETURNS trigger LANGUAGE 'plpgsql' AS $$
BEGIN
    INSERT INTO rpt.report_data_clean
    SELECT DATE_PART('year', payment_date) AS Year
         , address AS Location
         , CAST(amount AS money) AS Revenue
    FROM rpt.report_data;
    RETURN NULL;
END;
$$;
ALTER FUNCTION rpt.FN_Clean_Data() OWNER TO postgres;
COMMENT ON FUNCTION rpt.FN_Clean_Data()
IS 'New data in rpt.report_data gets cleaned and inserted into rpt.report_data_clean';

CREATE TRIGGER TR_ETL AFTER INSERT ON rpt.report_data
    FOR STATEMENT
    EXECUTE FUNCTION rpt.FN_Clean_Data();
COMMENT ON TRIGGER TR_ETL ON rpt.report_data
IS 'Update reports when new data is added to the rpt.report_data table';
/*========================================================================*/
CREATE OR REPLACE FUNCTION rpt.FN_ETL() RETURNS trigger LANGUAGE 'plpgsql' AS $$
BEGIN
    TRUNCATE TABLE rpt.location_trended;
    INSERT INTO rpt.location_trended
    SELECT "Year", "Location", SUM("Revenue")
    FROM rpt.report_data_clean
    GROUP BY "Year", "Location";

    TRUNCATE TABLE rpt.location_top;
    INSERT INTO rpt.location_top
    SELECT "Year", "Location", SUM("Revenue")
         , RANK() OVER(ORDER BY "Year" DESC, SUM("Revenue") DESC) AS "Rank"
    FROM rpt.report_data_clean
    WHERE "Year" IN (
        --   CAST(DATE_PART('year', NOW()) AS INT)     -- Current Year
        -- , CAST(DATE_PART('year', NOW()) AS INT) - 1 -- Prior Year
          (SELECT MAX("Year") FROM rpt.report_data_clean)
        , (SELECT MAX("Year") - 1 FROM rpt.report_data_clean)
    )
    GROUP BY "Year", "Location";
    RETURN NULL;
END
$$;
ALTER FUNCTION rpt.FN_ETL() OWNER TO postgres;
COMMENT ON FUNCTION rpt.FN_ETL()
IS 'New data in rpt.report_data_clean so update all reports';

CREATE TRIGGER TR_Update_Reports AFTER INSERT ON rpt.report_data_clean
FOR STATEMENT
EXECUTE FUNCTION rpt.FN_ETL();
COMMENT ON TRIGGER TR_Update_Reports ON rpt.report_data_clean
IS 'Update reports when new data is added to the rpt.report_data_clean table';
```



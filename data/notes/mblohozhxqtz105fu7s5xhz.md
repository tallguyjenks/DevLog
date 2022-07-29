


```sql

CREATE OR REPLACE FUNCTION rpt."FN_Nuke_From_Orbit"() RETURNS void LANGUAGE 'plpgsql' AS $$
BEGIN
    TRUNCATE TABLE rpt.report_data;
    TRUNCATE TABLE rpt.report_data_clean;
    TRUNCATE TABLE rpt.location_trended;
    TRUNCATE TABLE rpt.location_top;
END;
$$;
ALTER FUNCTION rpt."FN_Nuke_From_Orbit"() OWNER TO postgres;
COMMENT ON FUNCTION rpt."FN_Nuke_From_Orbit"()
IS 'Wipe all data in the rot schema from the Face of the earth';

CREATE OR REPLACE PROCEDURE rpt."USP_Refresh"() LANGUAGE 'plpgsql' AS $$
BEGIN
    /*********************************************************
    USAGE:
        This stored procedure can be run at any interval desired.
        Since this performs a full truncate and load of the entire
            rpt schema and all table data this will be expensive
            in resources.
        Recommendation is, depending on geographic factors of
            store locations affecting end of day accounting totals,
            to run the stored procedure in the off hours such as 
            at midnight or directly after C.O.B. so the day's
            results are posted immediately after the conclusion
            of that day's business.
    *********************************************************/
    /*********************************************************
    Wipe The entire structure of the rpt schema for a clean
    full rebuild via truncate and load ETL
    *********************************************************/
    PERFORM rpt."FN_Nuke_From_Orbit"();
    /*********************************************************
    Grab all raw data and kick off the live rebuild process
    driven by triggers.
    *********************************************************/
    INSERT INTO rpt.report_data
    SELECT p.payment_date
         , a.address
         , p.amount
    FROM public.payment AS p
        LEFT JOIN public.staff AS S ON s.staff_id = p.staff_id
        LEFT JOIN public.store AS st ON st.store_id = s.store_id
        LEFT JOIN public.address AS a ON a.address_id = st.address_id;
    COMMIT;
END;
$$;
COMMENT ON PROCEDURE rpt."USP_Refresh"()
IS 'Refresh the entire reporting structure';
```

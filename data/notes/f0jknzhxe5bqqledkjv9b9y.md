

## Make a New Run Books

### SC 2016 Service Manager

- ==Monitor Object==:
  - Monitoring For new or updated items
  - **Connection:** `SCSM PROD`
  - **Class:** `service request` or `incident`
    - One monitor for each class type
  - **Trigger:** Keep trigger to _New_ because _Update_ will do a biiiig pull
  - **Filters:** To match your criteria Title works with [[Regex|regex]]
- ==Update Object==
- ==Create Relationship==

## Utilities

- ==Write To Database==

## Text File Management

- ==Append Line==

## Tips

- **Data Fields:**
  - For input areas _right click_ to get `subscribe data` or `variables`
- **Data Connectors:** To connect nodes together and have data flow between nodes hover over an icon and it's arrow until the cursor changes to a black cross hairs then click and drag to another node. no visual indication of the operation will occur until the drag and drop is complete
  - The connector lines also have additional options you can access with double clicking

---

- Never just change ticket status to `Closed`
  - Change to `Completed` the `Closed` status is auto
  - Make sure to update comments or description with `implementation status` and `notes` so tickets are not just closed with no user communication
- ADM account doesnt have access to file location? then for 
  **Security** pass your normal credentials and the path to the location that your normal account has access to
  Best to have a service account own this though
  - Service account would need:
    - ADM Account
    - Access to @IT
    - Access to the SCORTCH AD group

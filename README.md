Created an S3 bucket named sf-s3-integration-sns with the following folders:
customer_contacts/: Contains the CSV file customer_contact.csv.
customer_transaction_opportunity/: Contains the CSV file corrected_snowflake_customer_transactions.csv.
Created an IAM policy and role.
Link IAM policy to the IAM role
Created a Snowflake integration to access the S3 bucket and its files.
Describe the created Snowflake integration to get “STORAGE_AWS_IAM_USER_ARN’ and “STORAGE_AWS_EXTERNAL_ID” , which required to added into  IAM role for  “Trust relationships”
Created a topic for AWS SNS and set up notifications for updates to the CSV files.
Created a Snowpipe for auto ingest the stage tables (CUSTOMER_CONTACT_STAGE and CUSTOMER_TRANSACTIONS_OPPORTUNITY_STAGE).
Created a “Snowflake dynamic table” (ENRICHED_DYNAMIC_CUSTOMER_CONTACT, and ENRICHED_DYNAMIC_CUSTOMER_OPPORTUNITY)  that checks the staging tables for any validations and updates itself at regular scheduled intervals.
Created a master table to consolidate from the dynamic table.
Calculated the RFM score on the master table.
Similarly, the customer_contacts and customer_transaction_opportunity from the Salesforce Cloud will be received by Snowflake -  yet to be set up.
Created the RFM score for enriched data using Snowflake SQL.
Finally, the ML model output, along with the RFM score, will be shared with Salesforce Data Cloud as a zero-copy object - yet to be set up.
Based on the shared data, Salesforce Cloud will handle target activation - yet to be set up.
Contact and opportunity will be updated using the Installed Salesforce data loader

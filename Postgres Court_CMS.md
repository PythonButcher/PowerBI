# Postgres Court_CMS Table Columns Metadata

| Schema | Table Name | Column Name | Data Type | Nullable | Key / Constraint |
| --- | --- | --- | --- | --- | --- |
| public | attorneys | attorney_id | integer | NO | PRIMARY KEY |
| public | attorneys | first_name | character varying | YES |  |
| public | attorneys | last_name | character varying | YES |  |
| public | attorneys | bar_number | character varying | YES | UNIQUE |
| public | attorneys | firm_name | character varying | YES |  |
| public | attorneys | role | character varying | YES |  |
| public | case_parties | case_party_id | integer | NO | PRIMARY KEY |
| public | case_parties | case_id | integer | YES | FOREIGN KEY |
| public | case_parties | person_id | integer | YES | FOREIGN KEY |
| public | case_parties | party_role | character varying | YES |  |
| public | case_status | case_status_id | integer | NO | PRIMARY KEY |
| public | case_status | status_name | character varying | YES | UNIQUE |
| public | cases | case_id | integer | NO | PRIMARY KEY |
| public | cases | case_number | character varying | YES | UNIQUE |
| public | cases | case_type_id | integer | YES | FOREIGN KEY |
| public | cases | case_status_id | integer | YES | FOREIGN KEY |
| public | cases | filing_date | date | YES |  |
| public | cases | court_id | integer | YES | FOREIGN KEY |
| public | cases | assigned_judge_id | integer | YES | FOREIGN KEY |
| public | cases | description | text | YES |  |
| public | charges | charge_id | integer | NO | PRIMARY KEY |
| public | charges | case_id | integer | YES | FOREIGN KEY |
| public | charges | offense_id | integer | YES | FOREIGN KEY |
| public | charges | charge_level | character varying | YES |  |
| public | charges | filed_date | date | YES |  |
| public | charges | is_primary | boolean | YES |  |
| public | court_case_type | case_type_id | integer | NO | PRIMARY KEY |
| public | court_case_type | case_type_code | character varying | YES | UNIQUE |
| public | court_case_type | description | character varying | YES |  |
| public | courts | court_id | integer | NO | PRIMARY KEY |
| public | courts | court_name | character varying | YES |  |
| public | courts | jurisdiction | character varying | YES |  |
| public | courts | court_level | character varying | YES |  |
| public | dispositions | disposition_id | integer | NO | PRIMARY KEY |
| public | dispositions | charge_id | integer | YES | FOREIGN KEY |
| public | dispositions | disposition_result | character varying | YES |  |
| public | dispositions | disposition_date | date | YES |  |
| public | hearings | hearing_id | integer | NO | PRIMARY KEY |
| public | hearings | case_id | integer | YES | FOREIGN KEY |
| public | hearings | hearing_type | character varying | YES |  |
| public | hearings | hearing_date | date | YES |  |
| public | hearings | courtroom | character varying | YES |  |
| public | hearings | result_summary | text | YES |  |
| public | judges | judge_id | integer | NO | PRIMARY KEY |
| public | judges | first_name | character varying | YES |  |
| public | judges | last_name | character varying | YES |  |
| public | judges | appointment_date | date | YES |  |
| public | judges | court_id | integer | YES | FOREIGN KEY |
| public | offenses | offense_id | integer | NO | PRIMARY KEY |
| public | offenses | statute_code | character varying | YES |  |
| public | offenses | offense_name | character varying | YES |  |
| public | offenses | severity_level | character varying | YES |  |
| public | payments | payment_id | integer | NO | PRIMARY KEY |
| public | payments | case_id | integer | YES | FOREIGN KEY |
| public | payments | payment_date | date | YES |  |
| public | payments | amount | numeric | YES |  |
| public | payments | payment_method | character varying | YES |  |
| public | people | person_id | integer | NO | PRIMARY KEY |
| public | people | first_name | character varying | YES |  |
| public | people | last_name | character varying | YES |  |
| public | people | date_of_birth | date | YES |  |
| public | people | gender | character varying | YES |  |
| public | people | ssn_last4 | character | YES |  |
| public | people | created_at | timestamp without time zone | YES |  |
| public | plea_type | plea_type_id | integer | NO | PRIMARY KEY |
| public | plea_type | plea_name | character varying | YES |  |
| public | pleas | plea_id | integer | NO | PRIMARY KEY |
| public | pleas | charge_id | integer | YES | FOREIGN KEY |
| public | pleas | plea_type_id | integer | YES | FOREIGN KEY |
| public | pleas | plea_date | date | YES |  |
| public | sentences | sentence_id | integer | NO | PRIMARY KEY |
| public | sentences | disposition_id | integer | YES | FOREIGN KEY |
| public | sentences | jail_days | integer | YES |  |
| public | sentences | probation_months | integer | YES |  |
| public | sentences | fine_amount | numeric | YES |  |
| public | sentences | community_service_hours | integer | YES |  |
| public | warrants | warrant_id | integer | NO | PRIMARY KEY |
| public | warrants | case_id | integer | YES | FOREIGN KEY |
| public | warrants | issue_date | date | YES |  |
| public | warrants | warrant_type | character varying | YES |  |
| public | warrants | is_active | boolean | YES |  |

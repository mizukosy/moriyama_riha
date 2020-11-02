# README

### teble

## therapists table
| colum    | type    | options                      |
| -------- | ------- | ---------------------------- |
| name     | string  | null:false                   |
| type_id  | integer | null:false, acceptance: true |
| exp_year | integer | null:false                   |

### Association
- has_many :patients, through thera_patients
- has_many :thera_patients

## thera_patients table
| colum         | type    | options                         |
| ------------- | ------- | ------------------------------- |
| therapists_id | string  | null:false, foregen_key: true   |
| patients_id   | integer | null:false, foregen_key: true   |

### Association
- has_one :therapists
- has_one :patients

## patients table
| colum       | type     | options                       |
| ----------- | -------- | ----------------------------- |
| name        | string   | null:false                    |
| tag         | integer  | null:false                    |
| location_id | integer  | null:false, acceptance: true  |
| unit        | integer  | null:false                    |
| time        | datetime | null:false, uniqueness: true  |
| disease_id  | integer  | null:false, acceptance: true  |

### Associatien
- has_many :therapists 
- has_one  :thera_patients

# Data for Memorable SQL book users
## Book available at [memorablesql.com](https://memorablesql.com)

## Code to copy/paste to add intitial values for animals.dogs table 



## Kiva Loan Data
The [kiva_loans_200.csv](https://github.com/discdiver/memorable-sql/blob/master/kiva_loans_200.csv) file contains 200 records from a Kiva Loan dataset via Kaggle.  

Original data source: https://www.kaggle.com/kiva/data-science-for-good-kiva-crowdfunding.
License CC0: Public Domain. 

My sampling and cleaning script: https://www.kaggle.com/discdiver/kiva-loans-downsize-for-sql.

### Kiva loan table creation code

```
CREATE TABLE loans.loan
(
    id serial NOT NULL,
    funded_amount numeric,
    loan_amount numeric,
    activity text,
    sector text,
    use text,
    country_code text,
    country text,
    region text,
    currency text,
    partner_id numeric,
    posted_time timestamp,
    disbursed_time timestamp,
    funded_time timestamp,
    term_in_months numeric, 
    lender_count int,
    tags text,
    borrower_genders text,
    repayment_interval text,
    "date" date,
    PRIMARY KEY (id)
);

```

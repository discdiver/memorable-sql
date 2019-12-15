# Data for Memorable SQL book users
## Book available at [memorablesql.com](https://memorablesql.com)

## Code to copy/paste to add intitial values for animals.dogs table

```sql
INSERT INTO animals.dogs 
VALUES 
  (1,  'Buster', '2019-02-11', 10.2,	4, 'beagle', 'tri'),
  (2, 'Betty', '2019-01-04', 22.3, 4, 'basset hound', 'brown'),
  (3, 'Barry', '2019-01-09', 62.0, 4, 'German Shepherd', 'grey'),
  (4, 'Billi', '2019-06-11', 33.3, 4, 'lab', 'brown'),
  (5, 'Brenda', '2019-02-13', 23.3, 3, 'mutt', 'black'),
  (6, 'Bria', '2019-08-24', 60.3, 4, 'beagle-collie', 'black, white'),
  (7, 'Carrot', '2019-03-01', 12.3, 4, 'mix', 'gray'),
  (8, 'Wilson', '2019-04-15', 45.3, 4, 'Shar-Pei', 'light brown'),
  (9, 'Tish', '2019-10-04', 29.3, 3, 'retriever', 'brown'),
  (10, 'Gunter', '2019-11-16', 6.3, 4, 'dachshund', 'black, white');
```


## Code to copy/paste to create schemas, tables, and data for adoptions and owners

```sql
-- create adoptions schema
CREATE SCHEMA adoptions
    AUTHORIZATION postgres;


-- create adoption table
CREATE TABLE adoptions.adoption
(
    adoption_id serial NOT NULL,
    pet_id integer,
    owner_id integer,
    adoption_date date,
    fee numeric,
    PRIMARY KEY (adoption_id)
)
WITH (
    OIDS = FALSE
);

ALTER TABLE adoptions.adoption
    OWNER to postgres;


--insert values into adoption
INSERT INTO adoptions.adoption
VALUES 
  (1, 5, 3, '2019-11-07', 90.00),
  (2, 2, 3, '2019-11-07', 45.00),
  (3, 6, 4, '2019-11-09', 90.00),
  (4, 3, 2, '2019-11-11', 90.00);


-- create people schema
CREATE SCHEMA people
    AUTHORIZATION postgres;

-- create owners table
CREATE TABLE people.owners
(
    owner_id serial NOT NULL,
    first_name text NOT NULL,
    last_name text NOT NULL,
    email text,
    phone bigint,
    PRIMARY KEY (owner_id)
)
WITH (
    OIDS = FALSE
);

ALTER TABLE people.owners
    OWNER to postgres;


-- insert values into owners table
INSERT INTO people.owners
VALUES 
    (1, 'Veronica', 'James', 'vj@vjvj.com', 1234567890),
    (2, 'Kurt', 'Smith', 'ks@kurtsmithis.com', 5678901111),
    (3, 'Julia', 'Okey', 'julia@okeydokeyj.com', 4567890000),
    (4, 'Will', 'Lee', 'wl@wlwl.com', NULL),
    (5, 'Shannon', 'Shoop', 'shoop@shoopy.com', 2224445555);
```

## More dogs to insert into animals.dogs

```sql
INSERT INTO animals.dogs
VALUES
    (11, 'Woofer', '2019-03-11', 16.6,	4, 'beagle', 'tri'),
    (12, 'Toto', '2019-06-11', 16.9, 4, 'beagle', 'tri');
    (13, 'Crunchy', '2019-02-26', 26.4,	4, 'corgi', 'brown'),
    (14, 'Fuzzball', '2019-05-22', 12.0, 4, 'corgi', 'orange'),
    (15, 'Rizzo', '2019-04-09', 16.0,	4, 'corgi', 'tri-colored');
```

## Kiva Loan Data
The [kiva_loans_200.csv](https://github.com/discdiver/memorable-sql/blob/master/kiva_loans_200.csv) file contains 200 records from a Kiva Loan dataset via Kaggle.  

Original data source: https://www.kaggle.com/kiva/data-science-for-good-kiva-crowdfunding.
License CC0: Public Domain. 

My sampling and cleaning script: https://www.kaggle.com/discdiver/kiva-loans-downsize-for-sql.

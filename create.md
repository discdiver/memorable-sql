```sql
-- all the code to create everything for Memorable SQL book 

-- create animals schema
CREATE SCHEMA animals
    AUTHORIZATION postgres;

-- create dogs table
CREATE TABLE animals.dogs
(
    dog_id serial NOT NULL,
    name text,
    arrival_date date,
    arrival_weight numeric,
    legs integer,
    breed text,
    color text,
    PRIMARY KEY (dog_id)
)
WITH (
    OIDS = FALSE
);

ALTER TABLE animals.dogs
    OWNER to postgres;
    
--insert values into dogs
INSERT INTO animals.dogs
VALUES 
  (1, 'Buster', '2019-02-11', 10.2,	4, 'beagle', 'tri'),
  (2, 'Billi', '2019-06-11', 33.3, 4, 'lab', 'brown'),
  (3, 'Bria', '2019-08-24', 60.3, 4, 'beagle-collie', 'black, white'),
  (4, 'Carrot', '2019-03-01', 42.3, 4, 'mix', 'orange'),
  (5, 'Wilson', '2019-04-15', 45.3, 4, 'Shar-Pei', 'light brown'),
  (6, 'Tish', '2019-10-04', 29.3, 3, 'retriever', 'brown'),
  (7, 'Gunter', '2019-11-16', 9.3, 4, 'dachshund', 'grey'),
  (8, 'Toto', '2019-06-11', 16.9, 4, 'beagle', 'tri'),
  (9, 'Sweetie', '2019-02-26', 26.4, 4, 'corgi', 'gray'),
  (10, 'Rizzo', '2019-04-09', 16.0,	4, 'corgi', 'tri-colored');
  
  
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


--insert values into adoption table
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
    (1, 'Veronica', 'James', 'vj@vjvjthis.com', 1234567890),
    (2, 'Kurt', 'Smith', 'ks@kurtsmiththis.com', 5678901111),
    (3, 'Julia', 'Okey', 'julia@okeydokeyjthis.com', 4567890000),
    (4, 'Will', 'Lee', 'wl@wlwlthis.com', NULL),
    (5, 'Shannon', 'Shoop', 'shoop@shoopythis.com', 2224445555);


--- create weights table 
CREATE TABLE animals.weights
(
    weight_id serial,
    weight_date date,
    weight numeric,
    ped_id integer,
    PRIMARY KEY (weight_id)
)
WITH (
    OIDS = FALSE
);

ALTER TABLE animals.weights
    OWNER to postgres;


-- insert values into weights table
INSERT INTO animals.weights
VALUES 
    (1, '2019-10-15', 61.2, 3),
    (2, '2019-10-15', 20.3, 2),
    (3, '2019-10-15', 69.5, 6),
    (4, '2019-10-15', 31.2, 4),
    (5, '2019-10-15', 20.9, 5),
    (6, '2019-11-15', 64.5, 3),
    (7, '2019-11-15', 44.2, 8),
    (8, '2019-11-15', 20.0, 2),
    (9, '2019-11-15', 70.3, 6);

```

---
title: "Examine A Query"
author: "Chris Albon"
date: 2018-06-17T00:00:00-07:00
description: "How to examine queries in an SQL database."
type: technical_note
draft: false
aliases: [/postgresql/basics/examine_a_query/]
---

## Create Table

{{< highlight sql >}}
-- Create table called adventurers
CREATE TABLE adventurers (
    -- string variable
    name varchar(255),
    -- integer variable
    age int,
    -- string variable
    race varchar(255),
    -- string variable
    weapon varchar(255)
)
{{< /highlight >}}

## Insert Row

{{< highlight sql >}}
-- Insert into the table adventurers
INSERT INTO adventurers (name, age, race, weapon)
VALUES ('Fjoak Doom-Wife', 28, 'Human', 'Axe'),
       ('Alooneric Cortte', 29, 'Elf', 'Bow'),
       ('Piperel Ramsay', 35, 'Elf', 'Sword'),
       ('Casimir Yardley', 14, 'Elf', 'Magic')
{{< /highlight >}}

## View Table

{{< highlight sql >}}
-- Retrieve rows from table
SELECT * FROM adventurers
{{< /highlight >}}
<table border="1" style="border-collapse:collapse">
<tr><th>name</th><th>age</th><th>race</th><th>weapon</th></tr>
<tr><td>Fjoak Doom-Wife</td><td>28</td><td>Human</td><td>Axe</td></tr>
<tr><td>Alooneric Cortte</td><td>29</td><td>Elf</td><td>Bow</td></tr>
<tr><td>Piperel Ramsay</td><td>35</td><td>Elf</td><td>Sword</td></tr>
<tr><td>Casimir Yardley</td><td>14</td><td>Elf</td><td>Magic</td></tr></table>

## Examine Query

Note: the lower the cost the better.

{{< highlight sql >}}
-- Examine the query: retrieve all rows from table
EXPLAIN SELECT * FROM adventurers
{{< /highlight >}}
<table border="1" style="border-collapse:collapse">
<tr><th>QUERY PLAN</th></tr>
<tr><td>Seq Scan on adventurers  (cost=0.00..10.50 rows=50 width=1552)</td></tr></table>

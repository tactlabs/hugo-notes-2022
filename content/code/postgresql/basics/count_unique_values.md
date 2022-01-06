---
title: "Count Unique Values"
author: "Chris Albon"
date: 2018-06-17T00:00:00-07:00
description: "How to count the number of unique values in a table in an SQL database."
type: technical_note
draft: false
aliases: [/postgresql/basics/count_unique_values/]
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

## Insert Rows

{{< highlight sql >}}
-- Insert into the table adventurers
INSERT INTO adventurers (name, age, race, weapon)
VALUES ('Fjoak Doom-Wife', 28, 'Human', 'Axe'),
       ('Alooneric Cortte', 29, 'Elf', 'Bow'),
       ('Piperel Ramsay', 35, 'Elf', 'Sword'),
       ('Casimir Yardley', 14, 'Elf', 'Magic')
{{< /highlight >}}

## Count Unique Values In Race

{{< highlight sql >}}
-- Count the number of unique values in the race column
SELECT COUNT (DISTINCT race) FROM adventurers
{{< /highlight >}}
<table border="1" style="border-collapse:collapse">
<tr><th>count</th></tr>
<tr><td>2</td></tr></table>
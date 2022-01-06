---
title: "Rename Columns In Views"
author: "Chris Albon"
date: 2018-06-17T00:00:00-07:00
description: "How to rename columns in views in an SQL database."
type: technical_note
draft: false
aliases: [/postgresql/basics/rename_columns_in_views/]
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
       ('Alooneric Cortte', 29, 'Human', 'Bow'),
       ('Piperel Ramsay', 35, 'Elf', 'Bow'),
       ('Casimir Yardley', 14, 'Elf', 'Bow')
{{< /highlight >}}

## Create View
{{< highlight sql >}}
-- Create view called elves containing with the column's renamed:
-- elven_name, elven_age, race, and elven_weapon
CREATE VIEW elves (elven_name, elven_age, race, elven_weapon) AS (
                        -- Select all rows from adventurers table
                        SELECT * FROM adventurers
                        -- Where the race is elf
                        WHERE race = 'Elf'
                      )
{{< /highlight >}}

## Retrieve View

{{< highlight sql >}}
-- Retrieve all rows from the view Elf
SELECT * FROM elves
{{< /highlight >}}
<table border="1" style="border-collapse:collapse">
<tr><th>elven_name</th><th>elven_age</th><th>race</th><th>elven_weapon</th></tr>
<tr><td>Piperel Ramsay</td><td>35</td><td>Elf</td><td>Bow</td></tr>
<tr><td>Casimir Yardley</td><td>14</td><td>Elf</td><td>Bow</td></tr></table>
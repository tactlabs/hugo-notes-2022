---
title: "All Unique Values In Two Tables"
author: "Chris Albon"
date: 2018-06-17T00:00:00-07:00
description: "How to find all unique values in two table in an SQL database."
type: technical_note
draft: false
aliases: [/postgresql/merging_and_joining/all_unique_values_in_two_tables/]
---

## Create Table Of Elves

{{< highlight sql >}}
-- Create table called elves
CREATE TABLE elves (
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

## Create Table Of Dwarves

{{< highlight sql >}}
-- Create table called dwarves
CREATE TABLE dwarves (
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

## Insert Rows Into Elf Table

{{< highlight sql >}}
INSERT INTO elves (name, age, race, weapon)
VALUES ('Dallar Woodfoot', 25, 'Elf', 'Bow'),
       ('Cordin Garner', 29, 'Elf', 'Bow'),
       ('Keat Knigh', 24, 'Elf', 'Sword'),
       ('Colbat Nalor', 124, 'Elf', 'Magic')
{{< /highlight >}}

## Insert Rows Into Dwarf Table

{{< highlight sql >}}
INSERT INTO dwarves (name, age, race, weapon)
VALUES ('Kalog', 23, 'Dwarf', 'Axe'),
       ('Dranar', 145, 'Dwarf', 'Bow'),
       ('Bratar', 12, 'Dwarf', 'Axe'),
       ('Dragga', 23, 'Dwarf', 'Axe')
{{< /highlight >}}

## Find The Combined Unique Values In Two Tables

{{< highlight sql >}}
-- Retrieve all weapons from elves
SELECT weapon FROM elves
-- Combine unique values with...
UNION
-- Retrieve all weapons from dwarves
SELECT weapon FROM dwarves
{{< /highlight >}}
<table border="1" style="border-collapse:collapse">
<tr><th>weapon</th></tr>
<tr><td>Bow</td></tr>
<tr><td>Bow</td></tr>
<tr><td>Sword</td></tr>
<tr><td>Magic</td></tr></table>
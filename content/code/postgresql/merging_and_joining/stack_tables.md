---
title: "Stack Tables"
author: "Chris Albon"
date: 2018-06-17T00:00:00-07:00
description: "How to stack tables in an SQL database."
type: technical_note
draft: false
aliases: [/postgresql/merging_and_joining/stack_tables/]
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

## Stack Tables On Top Of Eachother

{{< highlight sql >}}
-- All rows from elf table
SELECT * FROM elves
-- Stack on top of...
UNION ALL
-- All rows from dwarf table
SELECT * FROM dwarves
{{< /highlight >}}
<table border="1" style="border-collapse:collapse">
<tr><th>name</th><th>age</th><th>race</th><th>weapon</th></tr>
<tr><td>Dallar Woodfoot</td><td>25</td><td>Elf</td><td>Bow</td></tr>
<tr><td>Cordin Garner</td><td>29</td><td>Elf</td><td>Bow</td></tr>
<tr><td>Keat Knigh</td><td>24</td><td>Elf</td><td>Sword</td></tr>
<tr><td>Colbat Nalor</td><td>124</td><td>Elf</td><td>Magic</td></tr>
<tr><td>Kalog</td><td>23</td><td>Dwarf</td><td>Axe</td></tr>
<tr><td>Dranar</td><td>145</td><td>Dwarf</td><td>Bow</td></tr>
<tr><td>Bratar</td><td>12</td><td>Dwarf</td><td>Axe</td></tr>
<tr><td>Dragga</td><td>23</td><td>Dwarf</td><td>Axe</td></tr></table>
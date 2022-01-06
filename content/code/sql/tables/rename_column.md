---
title: "Rename Column"
author: "Chris Albon"
date: 2019-01-28T00:00:00-07:00
description: "How to rename a column in Snowflake using SQL."
type: technical_note
draft: false
aliases: [/sql/tables/rename_column/]
---

## Create Table Of Superheroes

{{< highlight sql >}}
-- Create a table called SUPERHEROES. If it already exists, replace it.
CREATE OR REPLACE TABLE SUPERHEROES (
  -- Column called ID allowing up to five characters
  "ID" VARCHAR(5), 
  -- Column called NAME allowing up to 100 characters
  "NAME" VARCHAR(100),
  -- Column called ALTER_EGO allowing up to 100 characters
  "ALTER_EGO" VARCHAR(100)
);
{{< /highlight >}}

## Insert Rows For Each Superhero

{{< highlight sql >}}
-- Insert rows into SUPERHEROES
INSERT INTO SUPERHEROES 
    -- With the values
    VALUES
    ('XF6K4', 'Chris Maki', 'The Bomber'),
    ('KD5SK', 'Donny Mav', 'Nuke Miner');
{{< /highlight >}}

## View Table Of Superheroes

{{< highlight sql >}}
-- View the SUPERHEROES table
SELECT * FROM SUPERHEROES;
{{< /highlight >}}
<table border=1>
    <thead>
        <tr>
            <th>ID</th>
            <th>NAME</th>
            <th>ALTER_EGO</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>XF6K4</td>
            <td>Chris Maki</td>
            <td>The Bomber</td>
        </tr>
        <tr>
            <td>KD5SK</td>
            <td>Donny Mav</td>
            <td>Nuke Miner</td>
        </tr>
    </tbody>
</table>

## Rename A Column

{{< highlight sql >}}
-- Alter the SUPERHEROES table by...
ALTER TABLE IF EXISTS SUPERHEROES 
-- Renaming the ALTER_EGO column to "ALIAS"
RENAME COLUMN ALTER_EGO to ALIAS
;
{{< /highlight >}}

## View Table Of Superheroes

{{< highlight sql >}}
-- View the SUPERHEROES table
SELECT * FROM SUPERHEROES;
{{< /highlight >}}
<table border=1>
    <thead>
        <tr>
            <th>ID</th>
            <th>NAME</th>
            <th>ALIAS</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>XF6K4</td>
            <td>Chris Maki</td>
            <td>The Bomber</td>
        </tr>
        <tr>
            <td>KD5SK</td>
            <td>Donny Mav</td>
            <td>Nuke Miner</td>
        </tr>
    </tbody>
</table>
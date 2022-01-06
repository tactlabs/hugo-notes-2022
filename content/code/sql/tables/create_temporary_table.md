---
title: "Create Temporary Table"
author: "Chris Albon"
date: 2019-01-28T00:00:00-07:00
description: "How to create a temporary table using SQL in Snowflake."
type: technical_note
draft: false
aliases: [/sql/tables/create_temporary_table/]
---

## Create Temporary Table

The temporary table will last until the session ends.

{{< highlight sql >}}
-- Create a table called SUPERHEROES.
CREATE OR REPLACE TEMP TABLE SUPERHEROES (
  -- Column called ID allowing up to five characters
  "ID" VARCHAR (5), 
  -- Column called NAME allowing up to 100 characters
  "NAME" VARCHAR(100),
  -- Column called ALTER_EGO allowing up to 100 characters
  "ALTER_EGO" VARCHAR(100),
  -- Column called BANK_BALANCE allowing 38 digits with 2 after the decimal point
  "BANK_BALANCE" NUMBER(38, 2)
);
{{< /highlight >}}
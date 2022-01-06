---
title: "Delete Table"
author: "Chris Albon"
date: 2018-06-17T00:00:00-07:00
description: "How to delete table in an SQL database."
type: technical_note
draft: false
aliases: [/postgresql/tables/delete_table/]
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

## Delete Table

{{< highlight sql >}}
-- Delete table
DROP TABLE adventurers
{{< /highlight >}}
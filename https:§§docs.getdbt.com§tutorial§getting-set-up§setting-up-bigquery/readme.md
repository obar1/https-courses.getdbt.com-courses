
# <https:§§docs.getdbt.com§tutorial§getting-set-up§setting-up-bigquery>
> <https://docs.getdbt.com/tutorial/getting-set-up/setting-up-bigquery>

Set up and connect BigQuery

## Introduction

Setting up a new BigQuery instance
Accessing sample date in a public data set
Connecting dbt Cloud to BigQuery

## Prerequisites

need of gcp account

create a new project  - opt

## Loading data

access to public dataset
```
select * from `dbt-tutorial.jaffle_shop.customers`;
select * from `dbt-tutorial.jaffle_shop.orders`;
select * from `dbt-tutorial.stripe.payment`;
```

create dataset
jaffle_shop
stripe

## Connecting to dbt Cloud

Generate BigQuery credentials

create bq api key
![](2022-08-11-18-50-43.png)

simple setup
![](2022-08-11-18-51-32.png)

now you have the key
![](2022-08-11-18-52-51.png)

export the private key
![](2022-08-11-18-53-08.png)

go to dbt cloud

settings 
![](2022-08-12-12-07-17.png)

![](2022-08-12-12-08-07.png)

upload the json file exported

setup repo
![](2022-08-12-12-09-21.png)


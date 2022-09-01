
# <https:§§docs.getdbt.com§guides§getting-started§getting-set-up§setting-up-bigquery>
> <https://docs.getdbt.com/guides/getting-started/getting-set-up/setting-up-bigquery>


Set up and connect BigQuery

## Introduction

Setting up a new BigQuery instance
Accessing sample date in a public data set
Connecting dbt Cloud to BigQuery

## Prerequisites

need of gcp account

create a new project  - opt

https://console.cloud.google.com/

## Setting up

https://console.cloud.google.com/bigquery


## Loading data

access to public dataset

```sql
select * from `dbt-tutorial.jaffle_shop.customers`;
select * from `dbt-tutorial.jaffle_shop.orders`;
select * from `dbt-tutorial.stripe.payment`;
```

create dataset
- jaffle_shop
- stripe

## Connecting to dbt Cloud

Generate BigQuery credentials

create bq api key
![](2022-08-11-18-50-43.png)

https://console.cloud.google.com/apis/credentials/wizard

simple setup
![](2022-08-11-18-51-32.png)

dbt-user
BigQuery Admin in the Role field

now you have the key
![](2022-08-11-18-52-51.png)

export the private key
![](2022-08-11-18-53-08.png)

dbt-user-creds.json
> added to .gitignore

## Create a dbt Cloud account

https://cloud.getdbt.com/

settings 
![](2022-08-12-12-07-17.png)

![](2022-08-12-12-08-07.png)

upload the json file exported

## Initialize your repository and start development

setup repo
![](2022-08-12-12-09-21.png)

![](2022-08-23-14-38-36.png)

start developing

![](2022-08-23-14-39-41.png)

![](2022-08-23-14-40-45.png)
Initialize your project.

![](2022-08-23-14-41-48.png)

![](2022-08-23-14-42-04.png)
> color changed


![](2022-08-23-14-43-30.png)
scratch pad and 
```
select * from `dbt-tutorial.jaffle_shop.customers`
```

![](2022-08-23-14-44-21.png) 
```
dbt run
```

check bq

![](2022-08-23-15-13-25.png)

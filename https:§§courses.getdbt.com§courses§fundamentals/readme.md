
# <https:§§courses.getdbt.com§courses§fundamentals>
> <https://courses.getdbt.com/courses/fundamentals>
        
dbt Fundamentals

## Welcome to dbt Fundamentals (4 minutes)

use dbt for transformartion
five key topics
- models
- sources
- tests
- documentation
- deployment

video and practice
exampler page
review page
quiz

dbt docs for reference

community

channel in slack ` learn on demand` channel


## faq

5 hours to complete the course
you get dbt fundamental badge
https://docs.getdbt.com/
https://community.getdbt.com/

general feedback/error reporting on contents training@dbtlabs.com

## Who is an analytics engineer? (20 minutes)

objectives
- data teams structure
- transition from etl to elt
- role of analytics eng
- dbt in modern data stack
- structure of dbt project

### Traditional Data Teams

data analysts and data eng 
![](2022-08-11-06-07-49.png)
![](2022-08-11-06-08-15.png)
data anlatyst query tables created by data eng
create reports
2 roles 
gap between them
data analyst know what to build
data eng know how to build it
rethink what a data team could be with dbt

### ETL and ELT

so far etl
extract some data
transforma some data
load some data 
etl managed by data eng
few additional skills sql, pythin etc
data is built, then more tools are needed for data update automation process

now edw are on the cloud
they can scale when needed

now for elt
extract
load and then transform
we focus now first for E and L
when data in there in the edw then we can focus on the T
`game changer`
![](2022-08-11-06-17-51.png)

new role of analytic eng
rethink how data team works together

### Analytics Engineer

https://www.getdbt.com/what-is-analytics-engineering/

new role analytics eng
focus on taking raw data and tranf data so data analyst to use
focus on the T
data eng focus on EL and mantain infra
![](2022-08-11-07-14-46.png)

![](2022-08-11-07-15-18.png)

no silo-ed people 
1 person can cover all of them

### The modern data stack and dbt

data sources 

data paltform
// store the data 
use dbt cloud or dbt core with adaptors

loaders
// move data from soruces to data platform

bi tools and ml model and op analytics
// use the data

![](2022-08-11-07-22-10.png)

dbt fits into
![](2022-08-11-07-22-24.png)
![](2022-08-11-07-22-42.png)
develop T pipeline usign sql-like statements def models creating dep between models

visualize with the graph
![](2022-08-11-07-23-14.png)

develope the model 
test the model
before shipping the model to run on prod data
write doc of the model
deploy the dbt project when ready


### Overview of an exemplar project

use sample prj to learn dbt

 - yml 
 to ake aware dbt of tables 
 - sql
 model to stage the data

![](2022-08-11-15-57-11.png)
lienage shows how models are dep on other models and navigate on each of these
stg are staging tbale
fct and dim are finale models
`dbt run` to build to actaul model

`dbt test` to run test
- yml
def test to be sure of the data quality incoming

`dbt docs genearte` gen docs for the models
you have lineage graph 

deplyment
use env def in dbt cloud
and merge code to master etc

### review
![](2022-08-11-17-54-02.png)
![](2022-08-11-17-54-27.png)


## Set up dbt Cloud (17 minutes)

### Learning Objectives

Load training data into your data platform
Set up an empty repository and connect your GitHub account to dbt Cloud.
Set up your warehouse and repository connections.
Navigate the dbt Cloud IDE.
Complete a simple development workflow in the dbt Cloud IDE.


### dbt, data platforms, and version control

you have dbt cloud and dbt core

dbt connects to a data platform
https://docs.getdbt.com/docs/supported-databases/

use of github or others
https://docs.getdbt.com/docs/dbt-cloud/cloud-configuring-dbt-cloud/cloud-using-a-managed-repository

### Setting up dbt Cloud and your data platform

advice of getting access to one of the follow data platforms: BigQuery, Databricks, Redshift, or Snowflake.



or already access
https://docs.getdbt.com/tutorial/getting-set-up/setting-up-bigquery#loading-data


### dbt Cloud IDE Overview
yml and sql are the ones used

we have sql runner 
dbt code
preview shows what the compile will be in actual execution
copile shows the raw sql code 
sbt code is sql-like with extension
use of jinja macros

model are in sql

use of lineage shows models dep 

you have cmd line interface to run cmds

the changes are committed like in git
![](2022-08-11-18-27-05.png)
uncommitted files have blue dots

use `__` to access to auto-complete 

### Overview of dbt Cloud UI

![](2022-08-11-18-29-14.png)

![](2022-08-11-18-29-21.png)

dev env, prod env

projects
![](2022-08-11-18-30-12.png)

integrations
api keys 
![](2022-08-11-18-31-08.png)


## Models (28 minutes + exercise)

### Build your first model

Explain what models are in a dbt project.
Build your first dbt model.
Explain how to apply modularity to analytics with dbt.
Modularize your project with the ref function.
Review a brief history of modeling paradigms.
Identify common naming conventions for tables.
Reorganize your project with subfolders.

models means to shape the data from what you have to what you need
in bdt models are just sql
piece of logic
under the `models` folder
![](2022-08-12-16-51-03.png)
you configure what models to be table or view
ddl amd dml are generated by dbt

https:§§courses.getdbt.com§courses§fundamentals/dim_customers.sql

```
{{ config (
    materialized="table"
)}}
```
to change from view to table

```
dbt run

dbt run -m modelxyz
```

### What is modularity?

use ctes
use final to get out data
![](2022-08-12-18-37-40.png)
first model stg models
take underlaying data and shape a bit
final model refactor and select from stg models
assemble the various parts
![](2022-08-12-18-38-49.png)


### Modularity and the ref functions

move the cte in separate models and 
use ref to ref them in the final model
![](2022-08-12-18-42-55.png)
lineage graph
![](2022-08-13-06-06-07.png)

### Quick history of data modeling
![](2022-08-13-06-06-51.png)
optimized to reduce data redundancy

today with modern data stack
![](2022-08-13-06-07-58.png)
![](2022-08-13-06-08-09.png)

### Naming conventions

sources
![](2022-08-13-06-08-53.png)

staging 
one to one with sources
![](2022-08-13-06-09-19.png)

interm
![](2022-08-13-06-09-34.png)

fact models
![](2022-08-13-06-10-05.png)

dim models
![](2022-08-13-06-10-15.png)

ex
![](2022-08-13-06-10-33.png)

### Reorganize your project

```
models/staging 
models/marts
```

![](2022-08-13-06-14-17.png)
ref don't change as we use names models

change the yml models section
![](2022-08-13-06-16-10.png)

### Practice

TODO:

### Exemplar

TODO:

### Review

-  models are select from source data 
- dbt run materialize the actual models into the target dwh
- use config and materialized directives
- use full-refresh to refresh the structure

use modularity use staging models
ref macro to build flexible models
use of lineage graph 
before we used normalized models
now focus how to build things

naming conventions
![](2022-08-13-12-06-54.png)
folder org
![](2022-08-13-12-07-13.png)


===
Sources (12 minutes + exercise)
Tests (17 minutes + exercise)
Documentation (16 minutes + exercise)
Deployment (11 minutes + exercise)
Survey and Next Steps (30 minutes)


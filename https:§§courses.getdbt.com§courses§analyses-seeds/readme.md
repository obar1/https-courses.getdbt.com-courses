
# <https:§§courses.getdbt.com§courses§analyses-seeds>
> <https://courses.getdbt.com/courses/analyses-seeds>

## Analyses and Seeds

### Learning Objectives
Explain the purposes of analyses in contrast to models
Explain the role of seeds in a dbt project
Write and compile analyses and find the compiled SQL in the targets folder
Add a seed to a project and materialize in the data warehouse
Select from, test, and documents seeds

### What are analyses?

![](2022-08-13-12-38-15.png)
![](2022-08-13-12-39-45.png)

### What are seeds?

load smal static data from csv
![](2022-08-13-12-40-40.png)
`dbt seed`
![](2022-08-13-12-41-51.png)


### Implementing analyses
![](2022-08-13-12-45-37.png)

dbt compile and get analysis into the folder
![](2022-08-13-12-46-24.png)

### Implementing seeds

![](2022-08-13-12-48-47.png)
dbt seed to materialize the table
use as usual using ref
![](2022-08-13-12-49-59.png)
add yml
![](2022-08-13-12-51-10.png)

### Practice

```csv
employee_id,email,customer_id
3425, mike@jaffleshop.com, 1
2354, sarah@jaffleshop.com, 6
2342, frank@jaffleshop.com, 8
1234, jennifer@jaffleshop.com, 9
```

### Exemplar

```sql
with payments as (
select * from {{ ref('stg_payments') }}
),

aggregated as (
select
sum(amount) as total_revenue
from payments
where status = 'success'
)

select * from aggregated
```

### Review

![](2022-08-13-12-56-28.png)


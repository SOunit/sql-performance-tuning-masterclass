# point / insight

- cost changes by table volume and selection data amount!!!

  - if table is big and selection is small, transform happens for smaller cost
  - if table is small then the cost is almost same, no transform

- sometimes transformer does not select best execution plan because of time and resource limitation
  - in that case, developers have to do this

# query transform sample

## Or expansion

- or operator prevent using index and leads to low performance

```
select * from sales where prod_id = 14 or promo_id = 33;
```

```
select * from sales where prod_id = 14
union all
select * from sales where promo_id = 33 and prod_id <> 14
```

## SubQuery UnNesting

- select all sales and check customers table

```
select * from sales where cust_id
in (select cust_id from customers)
```

- fetch only matched records

```
select sales.*
from sales, customers
where sales.cust_id = customers.cust_id;
```

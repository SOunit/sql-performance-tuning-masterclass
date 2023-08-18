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

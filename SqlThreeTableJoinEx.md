```mysql
select a.account_id, c.fed_id, e.fname, e.lname
from account a inner join customer c
on a.cust_id = c.cust_id
inner join employee e
on a.open_emp_id = e.emp_id
where c.cust_type_cd = 'B';
```

* obviously the `on` between account and customer could be shortened
with the `using(cust_id)` subclause

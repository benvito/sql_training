# Ex. 00:

```sql
SELECT pz.name, pz.rating FROM person_visits pv
RIGHT JOIN pizzeria pz ON pv.pizzeria_id = pz.id
WHERE pv.pizzeria_id IS NULL
```
![image](https://github.com/benvito/sql_training/assets/72844642/89136690-548c-4953-a545-24ad0cf21513)

# Ex. 01:

```sql
SELECT all_time::date
	FROM (SELECT pv.visit_date 
		  FROM person_visits pv
		  WHERE pv.person_id = '1' or pv.person_id = '2') pv_nulled
RIGHT JOIN generate_series('2022-01-01',
						  '2022-01-10', interval '1 day') all_time 
						  ON pv_nulled.visit_date = all_time
WHERE pv_nulled.visit_date IS NULL
```

![image](https://github.com/benvito/sql_training/assets/72844642/8ce337ad-360f-46fd-9c18-d2955e8149a0)


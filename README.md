# knex-CheatSheet
Cheat Sheet Showing traditional SQL Queries for KNEX Syntax


### SELECT

```sql

sql.select()
    .from("Products")
    
SELECT * FROM `Products`;

 
sql.select('productName')
    .from("Products")
    
SELECT `productName` FROM `Products`

sql.select('productName', 'productID')
    .from("Products")
    
select `productName`, `productID` from `Products`


sql.select('productName as name')
        .from('Products')  

select `productName` as `name` from `Products`
```
##### WHERE

```sql

sql.select()
        .from('Products')   
        .where({'productID' : 1})
        
select * from `Products` where `productID` = 1


sql.select()
        .from('Products')   
        .where({'productID' : 1})

select * from `Products` where not `productID` = 1

sql.select()
    .from('Products')   
    .whereBetween('productID', [ 0, 1])
    
select * from `Products` where `productID` between 0 and 1

sql.select()
    .from('Products')   
    .whereNotBetween('productID', [ 0, 1])
    
select * from `Products` where `productID` not between ? and ?


sql.select()
    .from('Products')   
    .whereIn('productID', [2,1,3])
    
select * from `Products` where `productID` in (?, ?, ?)

sql.select()
    .from('Products')   
    .whereNotIn('productID', [2,1,3])

select * from `Products` where `productID` not in (?, ?, ?)

sql.select()
    .from('Products')   
    .whereRaw(' productID IN (1,2,3 )')
    
select * from `Products` where  productID IN (1,2,3 )

```
 
 
 ### JOIN
 
 ```
 sql.select('*')
    .from('Products')   
    .innerJoin('ProductColors', 'Products.productID', 'ProductColors.productID')
    
select * from `Products` inner join `ProductColors` on `Products`.`productID` = `ProductColors`.`productID`

```

### ORDER BY

```sql

sql.select('*')
    .from('Products')   
    .orderBy('productName')
    
select * from `Products` order by `productName` asc


```

### LIMIT & OFFSET

```sql

sql.select('*')
    .from('Products')   
    .limit(5)
    .offset(5)
    
select * from `Products` limit ? offset ?
```


    
 

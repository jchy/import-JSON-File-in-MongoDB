# import-JSON-File-in-MongoDB
importing json file in mongo db,  Assignment_5436

## Problem Statement :~
### use Mockaroo
### create a 1000 size collection of the following schema

- product_name
- product_id
- product_rating
- currency
- price
- no_of_purchases
- qty_left

### Answer the following queries with
- To import the json file in terminal use the folllowing command :~
```js
 mongoimport --db db_name --collection collection_name --file data.json --port 27017  --jsonArray 
 ```
1. top 10 purchased items- Ans:~
- Ans:~
```js
     db.product.find().sort({no_of_purchases:-1}).limit(10)
```

2. top 10 cheapest items
- Ans:~
```js
    db.product.find().sort({price:1}).limit(10)
```

3. top items where qty remains in stock
- Ans:~
```js
    db.product.find().sort({qty_left:-1}).limit(10)
```

4. top 10 rated products
- Ans:~
```js
     db.product.find().sort({price:-1}).limit(10)
```
5. bottom 10 rated products
- Ans:~
```js
     db.product.find().sort({price:-1}).skip(990).limit(10)
```

6. from 11-20 top rated products
- Ans:~
```js
    db.product.find().sort({price:-1}).skip(10)limit(10)
```

7. find products with rating between 3 and 4, and sorted from descending order of rating, if the ratings are same, then show the alphabetic order of name of the product
- Ans:~
```js
     db.product.find({$and:[{product_rating:{$gte:3}},{product_rating:{$lte:4}}]}).sort({product_rating:1,product_name:1})
```

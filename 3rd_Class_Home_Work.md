

## 3rd Class Home Work

   
### Dataset

#

    db.inventory.insertMany([
    { item: "journal", qty: 25, size: { h: 14, w: 21, uom: "cm" }, status: "A" },
    { item: "notebook", qty: 50, size: { h: 8.5, w: 11, uom: "in" }, status: "A" },
    { item: "paper", qty: 100, size: { h: 8.5, w: 11, uom: "in" }, status: "D" },
    { item: "planner", qty: 75, size: { h: 22.85, w: 30, uom: "cm" }, status: "D" },
    { item: "postcard", qty: 45, size: { h: 10, w: 15.25, uom: "cm" }, status: "A" }
    ]); 


### 1. The find() Method
To query data from MongoDB collection, you need to use MongoDB's find() method.

    db.inventory.find({})

### 2. The pretty() Method
To display the results in a formatted way, you can use pretty() method.

    db.inventory.find({}).pretty()

### 3. The findOne() method
Apart from the find() method, there is findOne() method, that returns only one document.

    db.inventory.findOne({}).pretty()

### 4. AND in MongoDB
To query documents based on the AND condition, you need to use $and keyword. Following is the basic syntax of AND −

    db.inventory.find({$and:[{"item":"planner"},{"status": "D"}]}).pretty()

### 5. OR in MongoDB
To query documents based on the OR condition, you need to use $or keyword. Following is the basic syntax of OR −

    db.inventory.find({$or:[{"item":"planner"},{"status": "D"}]}).pretty()

### 5. Using AND and OR Together

    db.inventory.find({"qty": {$gt:30}, $or: [{"item": "planner"},{"Status": "D"}]}).pretty()

### 6. NOT in MongoDB
To query documents based on the NOT condition, you need to use $not keyword following is the basic syntax of NOT −

    db.inventory.find({ "qty": { $not: { $gt: "100" } } } ).pretty()

### 2. The find() Method skipping _id

    db.inventory.find({},{_id:0})

### 3. The find() Method using equality condtion

    db.inventory.find({qty:25},{_id:0})

### 5. Select query using where in condtion

    db.inventory.find( { item: { $in: [ 'paper', 'postcard' ] } } ).pretty();

### 6. Select query using or condtion

    db.inventory.find({$or:[{item:{in:['paper','planer']},{qty:75}],status:"A"},{_id:0}).pretty();

### 7. Select query using where GREATER THAN condtion

    db.inventory.find({$or:[{item: "notebook"},{item: "postcard"},{item:"journal"}],"qty":{$gt:50}},{_id:0}).pretty();

### 8. Select query using where GREATER THAN OR EQUAL condtion

    db.inventory.find({$or:[{item: "notebook"},{item: "postcard"},{item:"journal"}],qty:{$gte:50}},{_id:0}).pretty();

### 9. Select query using where NOT EQUAL condtion

    db.inventory.find({$or:[{item: "notebook"},{item: "postcard"},{item:"journal"}],qty:{$lt:500},qty:{$ne:45}},{_id:0}).pretty();




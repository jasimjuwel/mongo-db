

## 3rd Class Assignment

   
### Dataset

#

db.inventory.insertMany([
{ item: "journal", qty: 25, size: { h: 14, w: 21, uom: "cm" }, status: "A" },
{ item: "notebook", qty: 50, size: { h: 8.5, w: 11, uom: "in" }, status: "A" },
{ item: "paper", qty: 100, size: { h: 8.5, w: 11, uom: "in" }, status: "D" },
{ item: "planner", qty: 75, size: { h: 22.85, w: 30, uom: "cm" }, status: "D" },
{ item: "postcard", qty: 45, size: { h: 10, w: 15.25, uom: "cm" }, status: "A" }
]); 


# Select Query

db.inventory.find({})

# Select query skipping _id

db.inventory.find({},{_id:0})

# Select query using equality condtion

db.inventory.find({qty:25},{_id:0})

# Select query using equality condtion

db.inventory.find({qty:25},{_id:0})

# Select query using where in condtion

db.inventory.find({qty:75,item:{$in:['paper','postcard']}},{_id:0}).pretty();

# Select query using or condtion

db.inventory.find({$or:[{item:{in:['paper','planer']}},{qty:75}],status:"A"},{_id:0})

# Select query using where GREATER THAN condtion

db.inventory.find({$or:[{item: "Notebook"},{item: "postcard"},{item:"journal"}],qty:{$gt:50}},{_id:0})

# Select query using where GREATER THAN OR EQUAL condtion

db.inventory.find({$or:[{item: "Notebook"},{item: "postcard"},{item:"journal"}],qty:{$gte:50}},{_id:0})

# Select query using where NOT EQUAL condtion

db.inventory.find({$or:[{item: "Notebook"},{item: "postcard"},{item:"journal"}],qty:{$lt:500},qty:{$ne:45}},{_id:0})




# MongoDB $inc operator with string value
This repository demonstrates an uncommon error when using the `$inc` operator in MongoDB update queries.  The error occurs when using a string instead of an integer for the increment value.  The solution shows how to properly use the `$inc` operator to increment a numeric field.

## Bug
The following code snippet shows the incorrect usage of the `$inc` operator:
```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { field: '1' } });
```
This will not increment the `field` by 1, as expected. Instead, it may lead to unpredictable behavior.

## Solution
The solution involves using an integer instead of a string value:
```javascript
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { field: 1 } });
```
This will correctly increment the `field` by 1.
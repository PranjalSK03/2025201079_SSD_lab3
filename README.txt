1. curl -L -o sales.json https://raw.githubusercontent.com/neelabalan/mongodb-sample-dataset/main/sample_supplies/sales.json

2. mongoimport --uri "mongodb://localhost:27017" \
  --db sample_supplies --collection sales \
  --file sales.json

3. mongosh

4. use sample_supplies

5. function printjsononeline(x) {
  console.log(EJSON.stringify(x, {relaxed:true}))
} //This was required since printjsononeline is not built into mongosh.

6. db.sales_work.drop()

db.sales.aggregate([
  { $merge: { into: "sales_work", whenMatched: "fail", whenNotMatched: "insert" } }
]).toArray()   // consume the cursor

7. in 1 to 4 changed roll no. (in 1 also change the email and roll no.) runs on s"ales_work collection"

8. in 5 to 10 runs on "sales collection"

9. Each query was executed as a single line command wrapped with
   printjsononeline(...).

10. For each task, qk_query.txt contains the query,
   and qk_output.txt contains the one-line JSON result.


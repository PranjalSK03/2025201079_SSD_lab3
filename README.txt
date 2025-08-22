Name : Pranjal Singh Katiyar
Roll No : 2025201079

Folder structure : 
2025201079_lab3/
│
├── q1_query.txt
├── q1_output.txt
├── q2_query.txt
├── q2_output.txt
├── q3_query.txt
├── q3_output.txt
├── q4_query.txt
├── q4_output.txt
├── q5_query.txt
├── q5_output.txt
├── q6_query.txt
├── q6_output.txt
├── q7_query.txt
├── q7_output.txt
├── q8_query.txt
├── q8_output.txt
├── q9_query.txt
├── q9_output.txt
├── q10_query.txt
├── q10_output.txt
│
└── README.txt



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


# N1QL QUERIES
## Simple Query
`SELECT * FROM mytable doc WHERE doc.type = "city" LIMIT 5`

## Command Line Queries On Machine
`cbq --script="SELECT DISTINCT raw doc.myfield FROM mybucket doc"`

## Example Array Distinct
```
SELECT ARRAY_DISTINCT(doc.myarray[*].Location) as Locations
FROM mybucket doc
WHERE doc.OrderNo = "123456"
```

## Unnest
```
SELECT DISTINCT r.GroupType
FROM mybucket doc UNNEST doc.myarray r
WHERE doc.OrderNo = "123456"
```

## Query By Doc ID
```
SELECT doc.type
FROM mybucket doc
WHERE meta(doc).id = "ordertype-12346"
LIMIT 1
```

## Parse String and Concatenate
```
SUBSTR(doc.startDate, 4) || "-" || SUBSTR(doc.startDate, 0, 2) || "-" || SUBSTR(doc.startDate, 2, 2) as startDate
```

## Multiple Let
```
Let a = (SELECT FROM ETC), b = (SELECT FROM ETC)
SELECT t.name,
 ARRAY FIRST { "user": { "_id": m.id, "name": m.name } }
   FOR m IN mbrs WHEN v.userID = m.id
   END FOR v IN t.members END AS members,
 ARRAY FIRST { "project": { "_id": p.id, "title": p.title } }
   FOR p IN projs WHEN v.projectID = p.id
   END FOR v IN t.projects END AS projects
FROM default t USE KEYS ["teamtest"]
LET mbrs = (SELECT META(m).id,m.name FROM default m USE KEYS t.members[*].userID),
projs = (SELECT META(p).id,p.title FROM default p USE KEYS t.projects[*].projectID)
```

## In Select, Check If Array Item Exists
```
SELECT meta(doc).id as id, wo.OrderNo as OrderNo,
  CASE WHEN ARRAY_CONTAINS(doc.myarray[*].GroupType, "GROUND") = true THEN "GROUND" END as isGround
FROM mybucket doc
LET wo = (doc)
WHERE doc.type = "order"
AND doc.City = "Stamford"
LIMIT 100
```

## Select Statement Append Field Value From Another Table
```
SELECT DISTINCT doc.Employee_Name, doc.Employee_ID, doc.City,
  FIRST y.Division FOR y IN wc WHEN y.City = doc.Work_City END AS DIVISION
FROM mybucket doc
LET wc = (
  SELECT DISTINCT wc.Center, wc.Division
  FROM mybucket wc
  WHERE wc.type = "center"
  AND wc.Division = "A1"
)
WHERE wc.type = "qq"
AND wc.Division = "A1"
LIMIT 10
```

## WHERE IN
```
SELECT doc.*
FROM mybucket doc
WHERE "myValue" IN doc.myArray[*].myProperty
```

## WHERE IN LET
```
SELECT
  doc.LOCATION,
  TRUNC(SUM(TRUNC(doc.Length / 5280, 4)), 4) as miles
  FROM mybucket doc
LET maps = (
  SELECT ARRAY_DISTINCT(L1.myarray[*].Loc), L1.myarray[*].GroupType
  FROM mybucket L1 UNNEST L1.myarray
  WHERE meta(L1).id = $1
  AND L1.type = "order"
  LIMIT 1
)
WHERE doc.type = "maps"
AND doc.Loc IN maps[0].Loc
GROUP BY doc.Loc
ORDER BY doc.Loc asc
```

## Get All ID's As An Array
`ARRAY item.specialID FOR item IN mydoc END AS test`

## Get Records In Last Day
`DATE_DIFF_STR(NOW_UTC(), doc.lastEditedTime, "day") <= 30`

## Join Example
```
SELECT doc1.*, doc2.*
FROM mybucket doc1 JOIN mybucket doc2 ON KEYS "mydoctype2-" || doc1.mymatchingid
WHERE doc1.type = "mydoctype1"
AND doc2.type = "mydoctype2"
```

## Convert String To Number
TO_NUMBER()
```
SELECT meta(doc).id, SUM(TO_NUMBER(doc.myfield)) AS SUM
FROM mybucket doc
WHERE doc.order = "12343455"
GROUP BY doc.myfield, meta(doc).id
```

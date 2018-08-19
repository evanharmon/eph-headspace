# CURL RATE LIMIT

## Example File
```
#!/bin/bash -e

for x in `seq 1 10`;
do

for i in `seq 1 2`;
do

curl -v "https://localhost:8000" -H "Content-type: application/json" && echo "Requests Sent: $i" &

done

wait
sleep 1
echo "Volley $x"

done
```

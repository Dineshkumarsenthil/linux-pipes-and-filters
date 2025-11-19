# linux-pipes-and-filters
---
### 
```
grep "CALL_DROP" telecom.log
```
###
```
grep "CALL_DROP" telecom.log | awk -F',' '{print $3}'
```
###
```
sed '1d' segregated_log.csv
```
###
```
grep "CALL_DROP" segregated_log.csv | awk -F',' '{print $4}'
grep "CALL_DROP" segregated_log.csv | awk -F',' '{print $3}' | sort | uniq -c
```
###
```


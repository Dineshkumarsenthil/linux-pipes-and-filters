# linux-pipes-and-filters
---
### Filter log for a specific event with grep
```
grep "CALL_DROP" telecom.log
```
### Extract a field with awk (CELL ID)
```
grep "CALL_DROP" telecom.log | awk -F',' '{print $3}'
```
### Normalize field with sed (remove label and whitespace)
```
sed '1d' segregated_log.csv
```
### — Sort and count with sort + uniq –c
```
grep "CALL_DROP" segregated_log.csv | awk -F',' '{print $3}' | sort | uniq -c
```
### Add a header and limit results with head 
```
grep "CALL_DROP" segregated_log.csv | awk -F',' '{print $3}' | sort | uniq -c

```
### Extract IMSIs that experienced call drops 
```
grep -oE '[0-9]{15}' segregated_log.csv
```
### Filter call drops with RSRP worse than -105 dBm
```
 awk -F',' '$5 <-105{print $1, $2, $3, $4}' segregated_log.csv
awk -F'\t' 'BEGIN{print "CELL_ID"} NR>1{print $3}' segregated_log.csv | head
```
---
## Summary

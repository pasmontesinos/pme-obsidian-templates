---
type: dashboard
scope: professional
tags: 
creation: 2023-05-16
---

# [[Ongoing Tasks]]

## Overdue
```dataview
TASK
FROM "" AND #task
WHERE !completed AND
(
  (scheduled != null and scheduled < date(today)) OR
  (due != null and due < date(today))
)
```

## Today
```dataview
TASK
FROM "" AND #task
WHERE (
  (scheduled != null and scheduled = date(today)) OR
  (due != null and due = date(today))
)
```

## Waiting-for
```dataview
TASK
FROM "" AND #task AND #waiting-for
WHERE !completed 
```


## Pending
```dataview
TASK
FROM "" AND #task AND !#waiting-for
WHERE !completed AND contains(text, "#task")
AND (
  (scheduled = null)
)
SORT created desc
```

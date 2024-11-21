---
type: person
scope: professional
tags: 
creation: <% tp.date.now("YYYY-MM-DD") %>

title: 
company: 
team: 
---

# [[<% tp.file.title %>]]

## Notes
- 
- 


## Not completed tasks
```dataview
TASK
FROM "" AND #task 
WHERE !completed AND contains(text, "[[<% tp.file.title %>]]")
SORT file.cday ASC
```


## Meetings
```dataview
TABLE sumary AS "Summary"
FROM ""
WHERE file.frontmatter.type = "meeting"
AND contains(file.outlinks, [[<% tp.file.title %>]])
SORT file.cday DESC
```


## Feedback
```dataview
TASK
FROM #task AND #feedback 
WHERE contains(text, "[[<% tp.file.title %>]]")
SORT file.cday DESC
```

---
type: journal
date: <% tp.date.now("YYYY-MM-DD") %>
summary: " "
scope: professional
tags: 
creation: <% tp.date.now("YYYY-MM-DD") %>
---
# [[<% tp.file.title %>]]

## Start-of-Day Checklist
- [ ] Factorial
- [ ] E-mail
- [ ] Slack
- [ ] Meetings
- [ ] Tasks

## ToDo
```dataview
TASK
FROM "" AND #task
WHERE !completed 
AND (
  (scheduled != null and scheduled <= date(this.file.frontmatter.date)) OR
  (due != null and due <= date(this.file.frontmatter.date))
)
```

## Meetings
```dataview
TABLE summary AS "summary"
FROM ""
WHERE file.frontmatter.type = "meeting"
AND file.frontmatter.date = this.file.frontmatter.date
```

## Log



## Activity
### Tasks creation
```dataview
TASK
FROM "" AND #task
WHERE created != null AND created = date(this.file.frontmatter.date)
```

### Tasks completion
```dataview
TASK
FROM "" AND #task
WHERE completed 
AND completion != null AND completion = date(this.file.frontmatter.date)
```

### Notes creation
```dataview
TABLE type AS "Type", summary AS "summary"
FROM ""
WHERE file.frontmatter.creation != null AND file.frontmatter.creation = this.file.frontmatter.date
```

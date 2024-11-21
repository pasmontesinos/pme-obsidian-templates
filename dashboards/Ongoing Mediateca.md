```dataview
TABLE type as Type, started as Started, date(today) - file.mtime as "Since last edition"
FROM ""
SORT file.frontmatter.rate desc
WHERE file.frontmatter.started != NULL
  AND file.frontmatter.finished = NULL
  AND (file.frontmatter.type = "video"
  OR file.frontmatter.type = "talk"
  OR file.frontmatter.type = "book"
  OR file.frontmatter.type = "post"
  OR file.frontmatter.type = "podcast")
SORT file.frontmatter.started ASC
```

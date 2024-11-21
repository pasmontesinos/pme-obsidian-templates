
```dataview
TABLE type as Type, started as Started, date(now) - file.mtime as "Since last edition"
FROM ""
SORT file.frontmatter.rate desc
WHERE file.frontmatter.started != NULL
  AND file.frontmatter.finished = NULL
  AND file.frontmatter.type != "video"
  AND file.frontmatter.type != "talk"
  AND file.frontmatter.type != "book"
  AND file.frontmatter.type != "post"
  AND file.frontmatter.type != "podcast"
  AND file.frontmatter.type != "course"
SORT file.mtime DESC
```




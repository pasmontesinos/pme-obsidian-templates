
```dataview
TABLE type as Type, author as Author, source as Source, year as Year, rate as Rate
FROM ""
SORT file.frontmatter.rate desc
WHERE file.frontmatter.type = "video"
   OR file.frontmatter.type = "post"
   OR file.frontmatter.type = "book"
   OR file.frontmatter.type = "talk"
   OR file.frontmatter.type = "podcast"

```


---
layout: post
title:  "Regex frontmatter removal"
date:   2018-01-10 18:04:02 +0100
categories: code regex
author: Simon Loynes
---

I recently found the need to strip frontmatter from source markdown files. After far too long playing around with [regex101.com](https://regex101.com) I finally came up with the following expression to work the magic.

```typescript
// frontmatter removal
const regex = /^---(.|\n)*?---\n/;
```

Frontmatter is a code block found at the beginning of a file and is used to manage meta data for that page of content. I’m working with frontmatter in YAML format so the code block is enclosed with — characters.

The term Frontmatter originated with the publishing industry, referencing anything in the first section of a book, for example, a Table of Content, or a Preface.

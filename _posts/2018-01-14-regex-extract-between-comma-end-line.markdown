---
layout: post
title:  "Regex extract comma --> EOL"
date:   2018-01-14 18:04:02 +0100
categories: code regex
author: Simon Loynes
---

So, more regex, this time extracting the final value in a row of a csv file. This is one step in a task to convert a csv file into a tsv file. In this instance things were complicated by the string data within the csv containing commas.

```typescript
// final column in a row capture
const regex = /^.*,\s*(.*)$/g;
```

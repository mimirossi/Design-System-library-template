# Tokens

Design token files exported from Figma go here.

1. In Figma, open the Variables panel and export the collection as JSON (one file per collection or mode).
2. Upload the file to this folder. Keep the same file name on later exports so pages update on their own.
3. Reference it from a page:

````markdown
```tokens
file: tokens/light.tokens.json
path: color
```
````

Both Figma's native variable export and the W3C design tokens format (`$type` / `$value`) are read. `example.tokens.json` is sample data: delete it once real exports are in place.

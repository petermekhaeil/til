# Add an object to existing JSON using jq

```bash
# Optional: Create new JSON file `feed.json` with empy array.
jq -n '[]' > feed.json

# Append an object to the array from `feed.json` 
# and store the new JSON in `feed.json.tmp`
jq \
    --arg date "$date" \
    --arg title "$title" \
    '. += [{"date": $date, "title": $title}]' \
    feed.json > feed.json.tmp

# Replace temp file with original file.
mv feed.json.tmp feed.json
```

- `--arg content "$content"` creates a variable `$content` to be used within the `jq` tool.
- `'. += [{...}]' feed.json` appends a new object to the array from `feed.json`.
- `> feed.json.tmp` is redirecting the output of `jq` into a temporarily file.
- `mv feed.json.tmp feed.json` is replacing original file with the new temporarily file. Basically updating the original file with the new content.

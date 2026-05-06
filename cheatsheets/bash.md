---
title: "Bash Scripting Cheatsheet"
description: "Bash scripting patterns for automation"
tags: [cheatsheet, bash, scripting, automation]
---

# Bash Scripting Cheatsheet


## Script Header

```bash
#!/bin/bash
set -euo pipefail
IFS=$'\n\t'
```

## Variables & Strings

```bash
name="world"
echo "Hello, ${name}!"
echo "${name^^}"       # WORLD (uppercase)
echo "${name:0:3}"     # wor (substring)
echo "${#name}"        # 5 (length)
```

## Conditionals

```bash
if [[ -f "$file" ]]; then
    echo "File exists"
elif [[ -d "$dir" ]]; then
    echo "Directory exists"
else
    echo "Not found"
fi

# String comparison
[[ "$a" == "$b" ]]
[[ -z "$var" ]]  # Empty check
[[ -n "$var" ]]  # Non-empty check
```

## Loops

```bash
for item in "${array[@]}"; do
    echo "$item"
done

while read -r line; do
    echo "$line"
done < file.txt
```

## Functions

```bash
my_function() {
    local name="$1"
    echo "Hello, $name"
    return 0
}
my_function "World"
```

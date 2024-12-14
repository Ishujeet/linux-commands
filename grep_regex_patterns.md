# Regex Patterns for `grep`

This document contains commonly used regular expression patterns for mastering `grep`.

---

## **Character Classes**

### **`.` (dot)**
Matches **any single character** except a newline.
```bash
grep -E 'a.c' file.txt  # Matches "abc", "aXc", but not "ac"
```

### **`[ ]` (brackets)**
Matches **any single character** inside the brackets.
```bash
grep -E '[aeiou]' file.txt  # Matches any vowel
```

### **`[^ ]` (negated brackets)**
Matches **any single character NOT inside the brackets**.
```bash
grep -E '[^aeiou]' file.txt  # Matches consonants
```

### **`[a-z]`**
Matches **any character in the specified range**.
```bash
grep -E '[a-f]' file.txt  # Matches letters from 'a' to 'f'
```

---

## **Anchors**

### **`^`**
Matches the **beginning** of a line.
```bash
grep '^The' file.txt  # Matches lines starting with "The"
```

### **`$`**
Matches the **end** of a line.
```bash
grep 'end$' file.txt  # Matches lines ending with "end"
```

---

## **Quantifiers**

### **`*`**
Matches **zero or more occurrences** of the preceding character.
```bash
grep -E 'go*' file.txt  # Matches "g", "go", "goo", etc.
```

### **`+`**
Matches **one or more occurrences** of the preceding character.
```bash
grep -E 'go+' file.txt  # Matches "go", "goo", but not "g"
```

### **`?`**
Matches **zero or one occurrence** of the preceding character.
```bash
grep -E 'colou?r' file.txt  # Matches "color" and "colour"
```

### **`{n}`**
Matches **exactly `n` occurrences** of the preceding character.
```bash
grep -E '[0-9]{4}' file.txt  # Matches any four-digit number
```

### **`{n,}`**
Matches **at least `n` occurrences**.
```bash
grep -E '[0-9]{3,}' file.txt  # Matches numbers with 3 or more digits
```

### **`{n,m}`**
Matches **between `n` and `m` occurrences**.
```bash
grep -E '[0-9]{2,4}' file.txt  # Matches numbers with 2 to 4 digits
```

---

## **Groupings and Alternation**

### **`( )` (parentheses)**
Groups patterns together.
```bash
grep -E '(cat|dog)' file.txt  # Matches "cat" or "dog"
```

### **`|` (pipe)**
Alternation (OR operator).
```bash
grep -E 'apple|orange' file.txt  # Matches "apple" or "orange"
```

---

## **Escape Sequences**

### **`\`**
Escape special characters.
```bash
grep '\$100' file.txt  # Matches "$100"
```

### **`	`**
Matches a tab character.
```bash
grep -E 'word\t' file.txt  # Matches "word" followed by a tab
```

### **`\b`**
Matches a **word boundary**.
```bash
grep -E '\bword\b' file.txt  # Matches "word" as a whole word
```

---

## **Examples for Practice**

### **Example 1**
Find lines containing a three-digit number in `numbers.txt`.
```bash
grep -E '[0-9]{3}' numbers.txt
```

### **Example 2**
Find lines in `text.txt` that start and end with the same letter.
```bash
grep -E '^(.).*\1$' text.txt
```

### **Example 3**
Match lines in `data.txt` where a word is repeated consecutively (e.g., "go go").
```bash
grep -E '\b(\w+) \1\b' data.txt
```

---


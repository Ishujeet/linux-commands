# AWK Mastery: Questions and Answers

## Easy Questions

### Question 1: Print the first column from a text file.
#### Command:
```bash
awk '{print $1}' data.txt
```
#### Explanation:
- `$1` refers to the first field (column) in the file.
- `{print $1}` prints the first column for every line in the file.

---

### Question 2: Print lines that contain the word "apple".
#### Command:
```bash
awk '/apple/ {print}' fruits.txt
```
#### Explanation:
- `/apple/`: A pattern that matches lines containing "apple".
- `{print}`: Prints the entire line (default action).

---

### Question 3: Print the number of fields (columns) in each line of a file.
#### Command:
```bash
awk '{print NF}' data.txt
```
#### Explanation:
- `NF` is a special variable in `awk` that holds the number of fields in the current line.

---

### Question 4: Print the second and third columns from a file.
#### Command:
```bash
awk '{print $2, $3}' info.txt
```
#### Explanation:
- `$2` and `$3` refer to the second and third fields, respectively.
- Fields are printed with a space between them.

---

### Question 5: Print the last field from each line of a file.
#### Command:
```bash
awk '{print $NF}' list.txt
```
#### Explanation:
- `$NF`: Refers to the last field of the current line.
- This works dynamically, regardless of the number of fields in a line.

---

## Medium Questions

### Question 1: Print lines where the second field is greater than 100.
#### Command:
```bash
awk '$2 > 100 {print}' numbers.txt
```
#### Explanation:
- `$2 > 100`: Condition to check if the second field is greater than 100.
- `{print}`: Prints the matching lines.

---

### Question 2: Print the sum of the values in the first column.
#### Command:
```bash
awk '{sum += $1} END {print sum}' values.txt
```
#### Explanation:
- `sum += $1`: Adds the value of the first field to the `sum` variable.
- `END {print sum}`: Prints the total sum after processing all lines.

---

### Question 3: Replace the word "cat" with "dog" in the file and print.
#### Command:
```bash
awk '{gsub(/cat/, "dog"); print}' animals.txt
```
#### Explanation:
- `gsub(/cat/, "dog")`: Replaces all occurrences of "cat" with "dog" in the line.
- `{print}`: Prints the modified line.

---

### Question 4: Print only the lines with more than 3 fields.
#### Command:
```bash
awk 'NF > 3 {print}' data.txt
```
#### Explanation:
- `NF > 3`: Condition to check if the number of fields in a line is greater than 3.
- `{print}`: Prints the matching lines.

---

### Question 5: Extract and print unique values from the first column.
#### Command:
```bash
awk '!seen[$1]++ {print $1}' data.txt
```
#### Explanation:
- `!seen[$1]++`: Tracks whether the value in `$1` (first column) has been seen before.
- `{print $1}`: Prints unique values from the first column.

---

## Hard Questions

### Question 1: Calculate the average of the second column.
#### Command:
```bash
awk '{sum += $2; count++} END {if (count > 0) print sum / count}' data.txt
```
#### Explanation:
- `sum += $2`: Adds the value of the second column to `sum`.
- `count++`: Counts the number of lines.
- `END {print sum / count}`: Calculates and prints the average.

---

### Question 2: Print lines in reverse order (from the last line to the first).
#### Command:
```bash
awk '{lines[NR] = $0} END {for (i = NR; i > 0; i--) print lines[i]}' file.txt
```
#### Explanation:
- `lines[NR] = $0`: Stores each line in an array indexed by the line number.
- `for (i = NR; i > 0; i--)`: Iterates through the lines in reverse order.
- `print lines[i]`: Prints each line.

---

### Question 3: Print the field names from a CSV file (first line only).
#### Command:
```bash
awk 'NR == 1 {print}' data.csv
```
#### Explanation:
- `NR == 1`: Checks if the current line number is 1.
- `{print}`: Prints the first line (field names in a CSV).

---

### Question 4: Count the occurrences of each word in a file.
#### Command:
```bash
awk '{for (i = 1; i <= NF; i++) words[$i]++} END {for (w in words) print w, words[w]}' words.txt
```
#### Explanation:
- `for (i = 1; i <= NF; i++)`: Iterates over each field in the line.
- `words[$i]++`: Increments the count for each word.
- `END {for (w in words) print w, words[w]}`: Prints each word and its count.

---

### Question 5: Extract and print the top 3 highest values from the second column.
#### Command:
```bash
awk '{print $2}' data.txt | sort -nr | head -n 3
```
#### Explanation:
- `{print $2}`: Extracts the second column.
- `sort -nr`: Sorts the values in descending numerical order.
- `head -n 3`: Displays the top 3 values.

---


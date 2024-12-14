# Mastering `grep` Command: Questions and Answers

## Easy Questions

### Question 1:
**Find lines that contain the word "apple" in a file named `fruits.txt`.**

#### Answer:
```bash
grep 'apple' fruits.txt
```

---

### Question 2:
**Search for the string "error" in the file `log.txt`, but only show the line numbers where it appears.**

#### Answer:
```bash
grep -n 'error' log.txt
```

---

### Question 3:
**Check if the string "hello" exists in a file `greetings.txt`. If it does, print the line containing the string.**

#### Answer:
```bash
grep -i 'hello' greetings.txt
```

---

### Question 4:
**List all the lines in the file `animals.txt` that do not contain the word "dog".**

#### Answer:
```bash
grep -vi 'dog' animals.txt
```

---

### Question 5:
**Search for lines containing the word "cat" in the file `pets.txt`, but ensure that the search is case-insensitive.**

#### Answer:
```bash
grep -i 'cat' pets.txt
```

---

## Medium Questions

### Question 1:
**Search for lines containing the word "apple" or "orange" in a file called `fruits.txt`.**

#### Answer:
```bash
grep -E 'apple|orange' fruits.txt
```

---

### Question 2:
**Find all lines in the file `logfile.txt` that do not contain the word "success" but contain the word "failure".**

#### Answer:
```bash
grep 'failure' logfile.txt | grep -v 'success'
```

---

### Question 3:
**Search for the word "server" followed by any word in the file `network_log.txt`.**

#### Answer:
```bash
grep -E 'server \S+' network_log.txt
```

---

### Question 4:
**Show only the first 10 lines from the file `data.txt` that contain the word "urgent".**

#### Answer:
```bash
grep 'urgent' data.txt | head -n 10
```

---

### Question 5:
**Search for lines in the file `report.txt` that start with a number.**

#### Answer:
```bash
grep '^[0-9]' report.txt
```

---

## Hard Questions

### Question 1:
**Search for lines in the file `data.txt` that contain a date in the format `YYYY-MM-DD`.**

#### Answer:
```bash
grep -E '^[0-9]{4}-[0-9]{2}-[0-9]{2}$' data.txt
```

---

### Question 2:
**Search for lines in the file `log.txt` where the word "error" is repeated consecutively (e.g., "error error").**

#### Answer:
```bash
grep -E 'error error' log.txt
```

---

### Question 3:
**Find lines in `text.txt` that contain a word starting with "a" and ending with "e".**

#### Answer:
```bash
grep -E '\ba.*e\b' text.txt
```

---

### Question 4:
**Search for lines in `file.txt` that contain either "dog" or "cat" at the start of the line.**

#### Answer:
```bash
grep -E '^(dog|cat)' file.txt
```

---

### Question 5:
**Find all lines in `file.log` that contain a phone number in the format `(XXX) XXX-XXXX`.**

#### Answer:
```bash
grep -E '\([0-9]{3}\) [0-9]{3}-[0-9]{4}' file.log


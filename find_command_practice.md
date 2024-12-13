# Mastering the `find` Command

## **Easy Questions**

### 1. Find all files in the current directory (non-recursive).
```bash
find . -maxdepth 1 -type f
```

### 2. Find all directories in the current directory (non-recursive).
```bash
find . -maxdepth 1 -type d
```

### 3. Find all files in the `/home` directory (including subdirectories).
```bash
find /home -type f
```

### 4. Find all files in the current directory that were modified in the last 24 hours.
```bash
find . -type f -mtime -1
```

### 5. Find all files with the `.txt` extension in the current directory.
```bash
find . -type f -name "*.txt"
```

## **Medium Questions**

### 1. Find all files in the current directory and its subdirectories that are larger than 1GB.
```bash
find . -type f -size +1G
```

### 2. Find all files in the `/var/log` directory that were modified more than 7 days ago.
```bash
find /var/log/ -mtime +7
```

### 3. Find all empty files in the current directory and its subdirectories.
```bash
find . -type f -empty
```

### 4. Find all directories in the `/etc` directory that contain the word "config" in their name.
```bash
find /etc/ -type d -name "*config*"
```

### 5. Find all files in the `/home` directory that are owned by a specific user (replace `username` with the actual username).
```bash
find /home/ -type f -user username
```

## **Hard Questions**

### 1. Find all files in the `/tmp` directory that have permissions `644`.
```bash
find /tmp/ -type f -perm 644
```

### 2. Find all symbolic links in the `/usr` directory and display their target paths.
```bash
find /usr/ -type l
```

### 3. Find all files in the `/var` directory that are larger than 500MB and were modified in the last 3 days.
```bash
find /var/ -type f -mtime -3 -size +500M
```

### 4. Find all files in the current directory that were accessed within the last hour.
```bash
find . -type f -amin -60
```

### 5. Find all `.log` files in `/var/log` and delete them (confirmation for each file).
```bash
find /var/log/ -type f -name "*.log" -exec rm -i {} \;
```

---



# `ls` Command - Practice Questions & Answers

## **Easy Questions (Basics of `ls`)**

1. **List all files and directories in the current directory.**  
   **Answer:**  
   ```bash
   ls
   ```

2. **List all files and directories, including hidden ones, in the current directory.**  
   **Answer:**  
   ```bash
   ls -a
   ```

3. **Display the size of files and directories in a human-readable format.**  
   **Answer:**  
   ```bash
   ls -lh
   ```

4. **Sort files and directories by their modification time (newest first).**  
   **Answer:**  
   ```bash
   ls -lt
   ```

5. **Show only the directory names in the current directory, not their contents.**  
   **Answer:**  
   ```bash
   ls -d */
   ```

---

## **Medium Questions (Intermediate Level)**

1. **List files in the current directory and sort them by file size, largest first.**  
   **Answer:**  
   ```bash
   ls -lhS
   ```

2. **List all files and directories in the `/etc` directory, excluding `.` and `..` entries.**  
   **Answer:**  
   ```bash
   ls -lh /etc
   ```

3. **List the files in the current directory, displaying them in a single column.**  
   **Answer:**  
   ```bash
   ls -1
   ```

4. **List all files and directories in the current directory in reverse order (oldest first).**  
   **Answer:**  
   ```bash
   ls -ltr
   ```

5. **List all files and directories in the current directory along with their inode numbers.**  
   **Answer:**  
   ```bash
   ls -i
   ```

---

## **Hard Questions (Advanced Level)**

1. **List all files in the current directory, including hidden ones, but exclude directories.**  
   **Answer:**  
   ```bash
   ls -al | grep -v '^d'
   ```

2. **List all files and directories in the current directory, sorted by the time of last access (oldest first).**  
   **Answer:**  
   ```bash
   ls -lu -r
   ```

3. **List all files in the current directory that are exactly 100 bytes in size.**  
   **Answer:**  
   ```bash
   ls -l | awk '$5 == 100 {print $9}'
   ```

4. **List all directories (and only directories) in the `/var` directory, sorted by the number of files they contain.**  
   **Answer:**  
   ```bash
   find /var -type d -depth 1 | xargs -I {} bash -c 'echo -n "{} "; ls -1 "{}" | wc -l' | sort -n -k2
   ```

5. **List all files and directories in the current directory, displaying their sizes in blocks (instead of bytes).**  
   **Answer:**  
   ```bash
   ls -ls
   ```

---

# df Command - Questions & Answers

## Easy Questions

### ### Question 1:
**What is the default output of the `df` command? Describe each column in the output.**

**Answer:**

```bash
$ df
Filesystem     1K-blocks     Used Available Use% Mounted on
/dev/sda1      488281250 12345678 123456789  25% /
tmpfs           16344972        0  16344972   0% /dev/shm
tmpfs           16344972     1234  16343738   1% /run
```

Explanation:

The default output of df shows the disk usage in 1K blocks:

**Filesystem:** The name of the file system or device.
**1K-blocks:** Total size of the file system in 1K blocks.
**Used:** Amount of space currently used in 1K blocks.
**Available:** Amount of free space in 1K blocks.
**Use%:** Percentage of the file system that is currently used.
**Mounted on:** The mount point of the file system.

### ### Question 2:
**How can you use df to display the disk space usage of only the file system where your current working directory resides?**

**Answer:**

```bash
$ df .
```
Explanation:

This command displays the disk space usage for the file system that contains the current directory (.).


### Question 3:
**How can you use df to display the disk space usage in human-readable format (e.g., in KB, MB, GB)?**

**Answer:**

```bash
df -h
```
Explanation:

The -h option displays the disk space in a human-readable format using appropriate units like KB, MB, GB.

### ### Question 4:
**How can you use df to show the disk space usage for all file systems, including those with zero usage?**

**Answer:**

```bash
df -a
```
Explanation:

The -a option shows all file systems, including those with zero usage (e.g., pseudo-filesystems like devfs or tmpfs).

### Question 5:
How can you use df to show the file system usage of a specific directory or mount point? For example, show the disk usage for /home.

**Answer:**

```bash
df /home
```
Explanation:

This command will show the disk space usage for the file system where the /home directory is mounted.

Medium Questions
### Question 1:
How can you use df to display disk space usage for all file systems except the ones that are of type tmpfs?

**Answer:**

```bash
df -T | grep -v tmpfs
```
Explanation:

The -T option shows the file system types, and grep -v tmpfs excludes any lines that contain tmpfs, effectively filtering out tmpfs file systems.

### Question 2:
How can you use df to show disk usage with a specific unit, like displaying everything in megabytes (MB)?

**Answer:**

```bash
df -m
```
Explanation:

The -m option displays the disk space in megabytes (MB), which converts the values to a more human-readable format in terms of MB.

### Question 3:
How can you use df to display disk space usage for all mounted file systems, but only show the output for file systems that are at least 10% used?

**Answer:**

```bash
df -h | awk '$5+0 >= 10'
```
Explanation:

The awk command is used to filter the output, ensuring only file systems where the usage percentage is at least 10% are shown. The $5+0 removes the % sign and allows for numeric comparison.

### Question 4:
How can you use df to display the disk space usage in terms of 1K blocks instead of the default 512-byte blocks?

**Answer:**

```bash
df -k
```
Explanation:

The -k option displays the disk space in 1K blocks (1024 bytes), which is a standard block size for file system reporting.

### Question 5:
How can you use df to display only the file systems that are mounted with the ext4 file system type?

**Answer:**

```bash
df -T | grep ext4
```
Explanation:

The -T option displays the file system types, and grep ext4 filters the output to show only file systems that are of type ext4.

Hard Questions
### Question 1:
How can you use df to display the disk space usage for all file systems, showing the number of inodes used and free, in addition to the usual disk usage details?

**Answer:**

```bash
df -i
```
Explanation:

The -i option shows the inode usage, including the number of inodes used, free, and the percentage used.

### Question 2:
How can you use df to display the disk space usage for all file systems, but exclude the file systems mounted under /dev (e.g., devfs or tmpfs)?

**Answer:**

```bash
df -T | grep -v 'dev'
```
Explanation:

This command uses grep -v 'dev' to exclude any file systems whose name or mount point contains dev, effectively filtering out file systems like devfs or tmpfs.

### Question 3:
How can you use df to display the disk space usage for all file systems and show the output in a format that is sorted by the amount of available space (from highest to lowest)?

**Answer:**

```bash
df -h | sort -k 4 -n -r
```
Explanation:

The sort -k 4 -n -r sorts the output based on the 4th column (the "Available" column) in numeric order and in reverse (descending) order, showing file systems with the most available space first.

### Question 4:
How can you use df to display the disk space usage for all file systems, but only show the file systems that are mounted on directories (i.e., excluding special file systems like proc, sysfs, etc.)?

**Answer:**

```bash
df -T | grep -vE '^(proc|sysfs|tmpfs|devfs)'
```
Explanation:

The regular expression ^(proc|sysfs|tmpfs|devfs) is used to exclude file systems that are mounted under /proc, /sys, /tmpfs, and /devfs, which are considered special file systems.

### Question 5:
How can you use df to display the disk space usage in a human-readable format, showing the usage for all file systems except those with 0% usage?

Answer:

```bash
df -h | awk '$5+0 != 0'
```
Explanation:

The awk '$5+0 != 0' filters the output to exclude file systems with 0% usage in the "Use%" column. The +0 removes the % symbol and performs a numeric comparison.

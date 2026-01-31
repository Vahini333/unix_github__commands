

# 📘 Unix/Linux & Git/GitHub Command Line Notes

This repository contains structured notes from classes covering **Unix/Linux terminal basics** and **Git/GitHub commands**.
It serves as a quick reference for common command-line operations, file handling, text processing, and version control.

---

## 🖥️ Unix / Linux Command Line Basics

### 📍 Navigation

```bash
pwd
```

Displays the full path of the current directory.

```bash
ls
```

Lists all files and folders in the current directory.

```bash
cd folder_name
```

Moves into a specified directory.

```bash
cd ..
```

Moves up one level in the directory structure.

---

### 📁 Creating Files and Directories

```bash
mkdir folder_name
```

Creates a new directory.

```bash
mkdir -p folder_name/{sub1,sub2,sub3}
```

Creates a directory with multiple subdirectories.

```bash
touch file.csv
```

Creates an empty file.

---

### ✏️ Writing and Viewing Files

```bash
echo "Hello world" > file.tsv
```

Writes content to a file (overwrites if it exists).

```bash
echo "Nice to meet you" >> file.tsv
```

Appends content to the end of a file.

```bash
cat file.tsv
```

Prints the entire contents of a file.

```bash
less filename
```

Views large files with scrolling support.

```bash
clear
```

Clears the terminal display (does not delete files).

---

### 📦 Copying, Moving, Renaming, Deleting

```bash
cp folder_1/file.tsv -t folder_2
```

Copies a file to another directory.

```bash
mv folder_1/file.tsv folder_2
```

Moves a file to another directory.

```bash
mv folder_1 test
```

Renames a file or directory.

```bash
rmdir folder_name
```

Deletes an empty directory.

```bash
rm -rf folder_name
```

Force deletes a directory and all its contents ⚠️.

---

### 📚 Help and History

```bash
man cp
```

Opens the manual page for a command.

```bash
q
```

Exits the manual or pager.

```bash
history
```

Displays previously executed commands.

---

## 🔍 Searching, Matching, and Text Processing

### Pattern Matching

```bash
ls foldername/name*
```

Matches files starting with a specific prefix.

```bash
ls foldername/file[a-z]
```

Matches specific character ranges.

```bash
echo prefix-{a,b,c}
```

Brace expansion for generating multiple strings.

---

### File Merging and Redirection

```bash
cat file1 file2 file3 > combined_file
```

Merges multiple files into one.

```bash
ls -l filename non_existing_file > output.txt 2> error.txt
```

Redirects output and errors separately.

```bash
ls -l
```

Displays detailed file information.

---

### Pipes

```bash
command1 | command2
```

Sends output of one command as input to another.

---

### Previewing Files

```bash
head filename
```

Shows the first 10 lines.

```bash
head -n 20 filename
```

Shows the first *n* lines.

```bash
tail filename
```

Shows the last 10 lines.

```bash
(head -n 5; tail -n 5) < filename
```

Shows both top and bottom lines.

---

## 🧬 Bioinformatics Examples

### FASTA Validation

```bash
grep -v "^>" filename | grep --color "[^ATGC]"
```

Removes headers and highlights invalid nucleotide characters.

```bash
grep -v ">" flank.fasta
```

Extracts only sequence lines from a FASTA file.

```bash
grep -v ">" flank.fasta | wc -m
```

Counts total characters (bases).

```bash
grep -v ">" flank.fasta | wc -l
```

Counts sequence lines.

---

### GTF / Gene Searches

```bash
grep 'gene_id "GENE_ID"' filename
```

Finds lines containing a specific gene ID.

```bash
grep -o 'gene_id "GENE_ID"' filename
```

Prints only the matched gene ID.

```bash
grep -c 'gene_id "GENE_ID"' filename
```

Counts gene occurrences.

---

### Column Extraction

```bash
cut -f 2 filename.tsv | head
```

Extracts a specific column from a TSV file.

---

## 🌱 Git & GitHub Basics

### Repository Status & History

```bash
git status
```

Shows the current state of the repository.

```bash
git log
```

Displays commit history.

```bash
git diff
```

Shows differences between file versions.

---

### Saving Changes

```bash
git add filename
```

Stages changes for commit.

```bash
git commit -m "Commit message"
```

Saves changes to the repository history.

---

### Undoing Changes

```bash
git restore filename
```

Restores file changes before staging.

```bash
git restore --staged filename
```

Unstages a file.

---

### File Management

```bash
git rm filename
```

Deletes a tracked file.

```bash
git mv oldname newname
```

Renames or moves a tracked file.

---

### Remote Repositories

```bash
git pull origin master
```

Downloads updates from the remote repository.

```bash
git clone <repository_link>
```

Creates a local copy of a remote repository.

---

### Ignoring Files

```bash
touch .gitignore
```

Specifies files and directories Git should ignore.



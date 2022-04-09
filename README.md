# Duplicate file finder

A Python script to search for duplicate files in a given path (directory)

It has no dependecy on third-party packages

To use the script, having Python installed is enough.

## How to use

Open a Terminal or CMD and run the script using the command

```
python find_duplicates.py path/to/scan
```

path to be scanned must full path: e.g

C:\Users\username\Documents # windows or

/home/username/Documents # Linux or Mac

## How the script works

The script works in three steps to speed up searching

- First, for all files in the given path, group files that have the same size (different files having the same size is very likely)

- For files having the same size, caculate the hash of the file on the first 1024 bytes (called simple hash) and group them using key: hash on the first 1024 bytes plus the size - to avoid collisions on equal hashes in the first part of the file

- For all files with similar hash on the 1st 1024 bytes, get their hash on the full file - collisions will be duplicates

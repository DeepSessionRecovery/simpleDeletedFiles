import os

def find_deleted_files(path):
    """
    Find deleted files in the specified directory.

    Args:
        path (str): Directory path to search.

    Returns:
        list: List of deleted file paths.
    """
    deleted_files = []
    for root, dirs, files in os.walk(path):
        for file in files:
            file_path = os.path.join(root, file)
            if not os.path.exists(file_path):
                deleted_files.append(file_path)
    return deleted_files

def main():
    path = input("Enter directory path: ")
    deleted_files = find_deleted_files(path)
    if deleted_files:
        print("Deleted files found:")
        for file in deleted_files:
            print(file)
    else:
        print("No deleted files found.")

if __name__ == "__main__":
    main()
```

How it works:

//The script asks for a directory path.
//It walks through the directory and its subdirectories.
//For each file, it checks if the file exists using `os.path.exists`.
//If the file doesn't exist, it's considered deleted and added to the list.
//Finally, it prints the list of deleted files.

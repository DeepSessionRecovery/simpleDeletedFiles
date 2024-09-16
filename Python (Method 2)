import os
import scandir
import argparse

def find_deleted_files(path, file_extension=None):
    """
    Find deleted files in the specified directory.

    Args:
        path (str): Directory path to search.
        file_extension (str): Optional file extension filter.

    Returns:
        list: List of deleted file paths.
    """
    deleted_files = []
    try:
        for root, dirs, files in scandir.walk(path):
            for file in files:
                file_path = os.path.join(root, file)
                if file_extension and not file.endswith(file_extension):
                    continue
                if not os.path.exists(file_path):
                    deleted_files.append(file_path)
    except PermissionError as e:
        print(f"Permission denied: {e}")
    except Exception as e:
        print(f"Error: {e}")
    return deleted_files

def main():
    parser = argparse.ArgumentParser(description="Find deleted files")
    parser.add_argument("path", help="Directory path to search")
    parser.add_argument("-e", "--extension", help="File extension filter")
    args = parser.parse_args()

    deleted_files = find_deleted_files(args.path, args.extension)
    if deleted_files:
        print("Deleted files found:")
        for file in deleted_files:
            print(file)
    else:
        print("No deleted files found.")

if __name__ == "__main__":
    main()
```


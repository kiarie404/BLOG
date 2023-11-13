# File Handling in Rust
Reference -->  std::fs documentation  
This notes do not cover OS-specific file_manipulation operations.

## Files


Directory's components can be represented as an Iterator full of (File/Folder) abstractions called DirEntry

## Dealing with Directories
The Entries of a Directory/Folder are stored in an Iterator called ReadDir. 
The elements inside the ReadDir can either be entries to files or sub-folders. These elements/entries are abstracted by a special struct called : DirEntry  

    ## DirEntry
    - A DirEntry is an Abstraction of  File or a Subdirectory within a Parent Folder.   
    - You can decompose a DirEntry to a path using the fun : pub fn path(&self) -> PathBuf
    - You can get the metadata of that file/Folder : pub fn metadata(&self) -> Result<Metadata>
      - metadata contains info about : FileType(file, folder, symlink), length, last_modified, last accessed, permissions

    

To populate the ReadDir Iterator, 
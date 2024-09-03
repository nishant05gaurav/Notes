![image](https://github.com/imsushant12/Notes-and-Cheat-Sheets/assets/68695162/c901170c-529e-4fa7-8aae-3d7ddeaf75ee)
![image](https://github.com/imsushant12/Notes-and-Cheat-Sheets/assets/68695162/8334078f-549f-414a-afea-12f2642e4547)
![image](https://github.com/imsushant12/Notes-and-Cheat-Sheets/assets/68695162/511896cb-4b4c-4d4f-bd24-5a9929efcb44)
![image](https://github.com/imsushant12/Notes-and-Cheat-Sheets/assets/68695162/d44ab0c7-4004-4833-b282-56cbd81868d8)
![image](https://github.com/imsushant12/Notes-and-Cheat-Sheets/assets/68695162/89e34a08-d995-4eba-8943-3956d3a4de45)
![image](https://github.com/imsushant12/Notes-and-Cheat-Sheets/assets/68695162/40ea044d-b8a0-48a2-bfa5-786e79f72dfb)
![image](https://github.com/imsushant12/Notes-and-Cheat-Sheets/assets/68695162/d160d867-61f6-4f67-8f59-9f5366225519)
![image](https://github.com/imsushant12/Notes-and-Cheat-Sheets/assets/68695162/da382200-1397-41ae-847e-10d73b817fe6)
![image](https://github.com/imsushant12/Notes-and-Cheat-Sheets/assets/68695162/c6c40e36-0be9-45ad-a044-79cef292780a)
![image](https://github.com/imsushant12/Notes-and-Cheat-Sheets/assets/68695162/be672678-c824-48ab-9e0a-0a278799a246)
![image](https://github.com/imsushant12/Notes-and-Cheat-Sheets/assets/68695162/12e9b589-6b02-42d5-ada2-f158731c3a83)
![image](https://github.com/imsushant12/Notes-and-Cheat-Sheets/assets/68695162/1de6068d-fff7-47f5-86b6-c8fb4aad1212)
![image](https://github.com/imsushant12/Notes-and-Cheat-Sheets/assets/68695162/fbe256e6-599b-4884-9f11-cebd30cc658e)

- To know about **Kernel**:
    - Goto cd/boot/
    - List the files (using ``ls``). The last file is kernel.
    - Can also use the command: **``uname``**
- To know about any command: **``man``** command.

- **``tr``** command can be used to translate text.
  - Example (Translate the content of ``file.txt`` into upper case and store in ``upper.txt``):
    ```bash
    cat file.txt | tr a-z A-Z > upper.txt
    ```
- **``\``** symbol can be used to write the rest command on the next line.
- To checkout disk space: **``df``** command.
- To checkout disk usage stats: **``du``** command.
  - **Note**:
    ```
    df(disk free) looks at disk used blocks directly in filesystem metadata, hence it returns much faster. The du can only show info about the entire disk/partition. 
    ```
- In the **``head``** and **``tail``** command, we can use **``-n``** flag to view the required number of lines.
  - Example (view first 2 lines and last 4 lines):
    ```bash
    head -n 2 data.txt
    tail -n 4 data.txt
    ```
- To find some file, we can use the commands:
  - **``locate``**: eg- ``locate file.txt`` or ``locate "*.txt"``
  - **``find``**: Examples
    - Find all the directories in the current directory. 
        ```bash
        find . -type d
        ```
    - Find all the ``.txt`` type files.
        ```bash
        find . -type f -name "*.txt"
        ```
    - Find all the files that are modified more than 2 minutes ago but less than 10 minutes ago.
        ```bash
        find . -type f -mmin +2 -mmin -10
        ```
    - Important flags:
        ```
        -maxdepth : The depth to which the searching should go.
        -size : The size of the file or directory.
        -empty : The files that are empty.
        -perm : The permissions of the file.
        ```
- To run any previous command, we can use **``!command-name``** or **``!command-number``**.
- To add new user,its password, and then delete it:
  ```bash
  useradd User
  passwd User
  userdel User
  ``` 
- OS related and other important commands:
    1. OS- ``uname``
    2. type of OS- ``uname -o``
    3. architecture- ``uname -m``
    4. kernel version- ``uname -r``
    5. CPU details- ``lscpu``
    6. virtual memory stat- ``vmstat``
    7. fins group IDs- ``id``
    8. list open files- ``lsof``
    9. list all the active listening ports- ``netstat``
    10. list all processes and their status and resource usage - ``ps aux``
        - ``ps`` is process and ``aux`` means, 
            - a = show processes for all users
            - u = display the process's user/owner
            - x = also show processes not attached to a terminal
    - append something at end: ``>>`` 
- Operators:
    - **``&&``**: If the first command works then only the second command will execute.
    - **``||``**: If the first command fails then only the second command will execute.
    - Combine more commands:
        ```bash
        echo "hi" && {echo "second"; echo "third"}
        ```

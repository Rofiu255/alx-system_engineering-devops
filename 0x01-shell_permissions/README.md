shell permission
0x01. Shell, permissions 



Tasks
0. My name is Betty
mandatory
Score: 100.0% (Checks completed: 100.0%)

Create a script that switches the current user to the user betty.

    You should use exactly 8 characters for your command (+1 character for the new line)
    You can assume that the user betty will exist when we will run your script




1. Who am I
mandatory
Score: 100.0% (Checks completed: 100.0%)

Write a script that prints the effective username of the current user.


2. Groups
mandatory
Score: 100.0% (Checks completed: 100.0%)

Write a script that prints all the groups the current user is part of.



3. New owner
mandatory
Score: 100.0% (Checks completed: 100.0%)

Write a script that changes the owner of the file hello to the user betty.



4. Empty!
mandatory
Score: 100.0% (Checks completed: 100.0%)

Write a script that creates an empty file called hello.



5. Execute
mandatory
Score: 100.0% (Checks completed: 100.0%)

Write a script that adds execute permission to the owner of the file hello.

    The file hello will be in the working directory




6. Multiple permissions
mandatory
Score: 100.0% (Checks completed: 100.0%)

Write a script that adds execute permission to the owner and the group owner, and read permission to other users, to the file hello.

    The file hello will be in the working directory



7. Everybody!
mandatory
Score: 100.0% (Checks completed: 100.0%)

Write a script that adds execution permission to the owner, the group owner and the other users, to the file hello

    The file hello will be in the working directory
    You are not allowed to use commas for this script



8. James Bond
mandatory
Score: 100.0% (Checks completed: 100.0%)

Write a script that sets the permission to the file hello as follows:

    Owner: no permission at all
    Group: no permission at all
    Other users: all the permissions

The file hello will be in the working directory You are not allowed to use commas for this script



9. John Doe
mandatory
Score: 100.0% (Checks completed: 100.0%)

Write a script that sets the mode of the file hello to this:

-rwxr-x-wx 1 julien julien 23 Sep 20 14:25 hello

    The file hello will be in the working directory
    You are not allowed to use commas for this script






10. Look in the mirror
mandatory
Score: 100.0% (Checks completed: 100.0%)

Write a script that sets the mode of the file hello the same as olleh’s mode.

    The file hello will be in the working directory
    The file olleh will be in the working directory



11. Directories
mandatory
Score: 65.0% (Checks completed: 100.0%)

Create a script that adds execute permission to all subdirectories of the current directory for the owner, the group owner and all other users.

Regular files should not be changed




12. More directories
mandatory
Score: 100.0% (Checks completed: 100.0%)

Create a script that creates a directory called my_dir with permissions 751 in the working directory.



13. Change group
mandatory
Score: 65.0% (Checks completed: 100.0%)

Write a script that changes the group owner to school for the file hello

    The file hello will be in the working directory




14. Owner and group
#advanced
Score: 65.0% (Checks completed: 100.0%)

Write a script that changes the owner to vincent and the group owner to staff for all the files and directories in the working directory.



    GitHub repository: alx-system_engineering-devops
    Directory: 0x01-shell_permissions
    File: 100-change_owner_and_group



15. Symbolic links
#advanced
Score: 65.0% (Checks completed: 100.0%)

Write a script that changes the owner and the group owner of _hello to vincent and staff respectively.

    The file _hello is in the working directory
    The file _hello is a symbolic link




Repo:

    GitHub repository: alx-system_engineering-devops
    Directory: 0x01-shell_permissions
    File: 101-symbolic_link_permissions




16. If only
#advanced
Score: 65.0% (Checks completed: 100.0%)

Write a script that changes the owner of the file hello to betty only if it is owned by the user guillaume.

    The file hello will be in the working directory




Repo:

    GitHub repository: alx-system_engineering-devops
    Directory: 0x01-shell_permissions
    File: 102-if_only





17. Star Wars
#advanced
Score: 0.0% (Checks completed: 0.0%)

Write a script that will play the StarWars IV episode in the terminal.




Repo:

    GitHub repository: alx-system_engineering-devops
    Directory: 0x01-shell_permissions
    File: 103-Star_Wars



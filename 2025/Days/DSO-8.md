Chapter 5

"Not every user of a single operating system should have the same level of access to files and directories."

The root level user in linux is the most powerful - it can do pretty much anything.

Other users have more granular permissions, and are usually granted them on an as-needed basis. These users are typically sorted by groups that have similar functions, which makes assigning permissions and groups easier from an administration and security perspective.

When it comes to permissions, there are three levels:

R - permission to read. the user can only open and view a file.

W - permission to write. the user can view and edit the file.

X - permission to execute. the user can execute a file, but they might not be able to view or edit.

the chown command gives a user ownership of a file. (chown stands for change owner) the chgrp command gives a group ownership of a file. (change group)

ls -l or (list long) displays all of the contents of a directory, along with the permissions related to it.

a file will have a string of letters and dashes to the left of the file. these dashes and letters give information about the permissions and whether or not the item is a file or a directory.

'd' means its a directory, '-' means its a file.

Then there is a sequence of 9 letters that indicate what permissions the owner, the group and the last three represent all other users, 3 for each. These letters are a combiniation of the permissions we saw earlier, R, W, X. If the r,w, or x is replaced with a -, then that permission has not been given.

You can change permissions using chmod (change mode). Only the file owner or the root user can change file permissions.

chmod refers to each permission as an octal, which is a 8 digit system that starts with 0 and end with 7. 0 meaning no permissions, and 7 meaning all.

chmod 777 would be giving r,w,x permissions to the file owner, the group and all other users.

there is also UGO syntax. UGO stands for user, groups, others.

the operations are "-, +, =" to remove, add and set a permission respectively.

the entire syntax might look something like chmod u-w file.txt which would be removing the write permission from the file.txt.

There is a feature called umask that can change how default permissions are applied. This feature uses an octal and subtracts this number from the default value. By default, linux assigns 666 for files, and 777 for directories.

There are special exceptions for permissions.

    adding a 4 to the chmod call (for example 4744) allows a user to execute the file with the permissions of the owner but the permissions don't extend past the use of that file. This is called setting the SUID bit (setting user id)

    SGID or (setting group id) grants permissions of the file owner's group, rather than the file owner itself. to do this, you would a 2 to the chmod call.

    There is a permission bit called the sticky bit that can be set on a directory to allow a user to delete or rename files within a directory. This is a legacy feature and modern systems ignore it.

takeaways: permissions are very important and its key to be able to open a file and be able to determine what permissions are on a file/directory.

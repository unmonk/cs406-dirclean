# PatternCleanupScript
Shell script which cleans up a directory by deleting files that match particular patterns.

##Usage##
Make Executable: 

`chmod u+x dirclean`

Run Script:

`dirclean [--test] ROOT_DIRECTORY PATTERN...`
##Logic##
1. **Error Check:** 
 - Program called w/ enough arguments, if not print usage message & failure exit status.

2. **Decode Args:** 
 - if `--test` specified, find ROOT_DIRECTORY`, get list of patterns.

3. **Validate `ROOT_DIRECTORY`:** 
 - if invalid, print err w/ failure status.

4. **Loop Root Directory Entries:**
 - if entry regular file, determine if it matches `PATTERN`
 - if match, print message: state file being deleted, then delete it (`rm FILENAME`)

5. **On Success:**
 - Return value of `0` (`EXIT_SUCCESS`)
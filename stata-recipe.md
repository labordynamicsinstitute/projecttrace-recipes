Stata recipe
============
This is designed to allow for developing programs in a closed environment. It may also be followed in an open environment, 
allowing for later portability to a restricted environment (e.g., synthetic data validation).

Requirements
------------
- Access to some sort of local cache or mirror of the package repository
- In this case, Stata
- Project directory is /home/user/tmp/stata - adjust accordingly

Recipe
------
```
/* set the local install versions to the project directory */
sysdir set PLUS "/home/user/tmp/stata"
sysdir set PERSONAL "/home/user/tmp/stata"

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
/* this will ensure that the project directory contains a local copy */
/* Ensure the directories exist! */
global PROJDIR "/projects/user/xyz/project1"
sysdir set PLUS "${PROJDIR}/stata/plus"
sysdir set PERSONAL "${PROJDIR}/stata/personal"

/* from https://www2.vrdc.cornell.edu/news/synthetic-data-server/step-4-using-the-sds/#Packages 
   and https://gist.github.com/larsvilhuber/002ffc7fa96136426a4801e1470e0189#file-sds_initialize-do */

/* define all source directories here */
global REPEC "/cac/contrib/mirror/fmwww.bc.edu/repec/bocode"
global RDPACK "/cac/contrib/mirror/sites.google.com/site/rdpackages/rdrobust/stata"

/* install all packages here */
net install estout, from(${REPEC}/e) replace
net install rdrobust, from(${RDPACK}) replace

```

Caveats
-------
- For Stata packages on RePEC, this needs to be adjusted for each command, ordered by first letter of command


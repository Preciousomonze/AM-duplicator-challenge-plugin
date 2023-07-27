# AM-duplicator-challenge-plugin

# Duplicator Challenge
This plugin is the basis from which to solve the Duplicator challenge.

- Before you start, add the name in the Author entry of the plugin and the Author URI if you want to.

This test is a test intended to assess backend development skills. 
Here is what will have the most relevance in the evaluation of the test.
- Object-oriented programming
- Database table design
- Error management, In general, the code should be solid.

### The test
- Make a function that scans all the files in the home and saves for each entry the size and number of nodes. 
    -- For a file the size is the file size and the number of nodes is 1.
    -- For a folder the size is the sum of all files contained in the folder and the number of nodes is the number of files and folders contained in the folder.
- The scan result must be persistent and then saved in a specially created database table. 
    -- The database data must be structured in such a way that, if desired it will be possible to later implement a file search given the path and it will be possible to have the list of child files given a node
- Consider that scanning must also work for large sites so chunk management must be provided to avoid timeouts
- On the main page of the plugin there should be a run scan button that when pressed empties the table and regenerates the scan.
- In addition, the result must be displayed. Consider that this is a backend test so the visualization can also be a simple dump of an array
- When you deactivate the plugin all data relaviti to the plugin including the table should be removed

### Optional implementations
The test is considered passed if the scan function works, if you want to solve something more complex and have time available here are some optional developments

- Add to the settings page a field with which it is impossible to set that scanning is done via wp-cron every X hours.
    -- Note that if you want to implement this, you need the chunked function to run in backgroud without using javascript, so the logic changes a bit.
- Add the ability to do a search by path or with the wildcard * or even a regex pattern on result page
- If desired, you can enhance the style of the view by showing the scan result with a tree.
    -- In this case, if you want to use an external javascript library to manage the tree is ok

### Additional Notes
- You cannot import external libraries, the only allowed functions are native PHP and wordpress core. 
- The "composer phpcs ."  command should not generate errors
    -- The formatting is set up so that you must enter the PHPDoc for each function.
        'composer install'  to install phpcs
        'composer phpcs .' to check
        'composer phpcbf .' to fix fixable format errors
- The code must work on PHP 5.6.20

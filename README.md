PHP class for the Dreamhost API
===============================

Interfaces with the Dreamhost API

Usage
-----

    $dreamhost = new dreamhost(your api key);
    $dreamhost->exec(command, Array(arg=>value,...));

Where command is one of the many listed on the Dreamhost Wiki API article.

exec returns either an array of associative arrays of the data returned by Dreamhost or throws an exception upon error.

Example
-------

    $dreamhost = new dreamhost('your api key');
    $cmd = "api-list_accessible_cmds";
    try {
        print_r($dreamhost->exec($cmd));
        // print_r($dreamhost->$cmd()); // this would also work
    }
    catch (Exception $e) {
        echo $e->getMessage(); // contains either the error data returned by dreamhost or a curl error string and number
    }
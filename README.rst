Mysql_Query_Session_Stats_Diff
===================

This script will take a given query (ex. "select * from table") and run a
"show session status" before and after that query. This script replaces
the need to dump the output of queries to a file and vimdiff. This script
is helpful for query performance tuning, making it easy to see how a query
will impact your MySQL performance statistics.

The output of the script is the Delta between the two runs of the
"show session status" command

This script requires DocOpt (Pythonic command line arguments parser, that
will make you smile http://docopt.org). Also check out their github page
at https://github.com/docopt/docopt 


.. code:: python

    Usage: queryStats [-v] -h HOST [-d DATABASE] (-s SOCKET | --port PORT) -u USERNAME -p [-f FILTER] -q QUERY ...

    Options:
    --help                  Print this help info.
    -h --host HOSTNAME      Specify MySQL hostname to connect to [default: localhost].
    -d --db DATABASE        Specify MySQL database [default: mysql].
    -s --socket SOCKET      Specify connection socket.
    -P --port PORT          Specify connection port [default: 3306].
    -u --username USERNAME  Specify your MySQL username.
    -p --password           Password mode.
    -f --filter FILTER      Specify filter keyword.
    -q --query QUERY        Specify Mysql query.
    -v --verbose            Specify to use verbose mode


Example usage:

.. code:: bash

    % python queryStats -h localhost -d mysql -P 3306 -u ryan -p -q "Select * from users.information where user_id LIKE admin"
    Password:
    hostname: localhost
    database: mysql
    port: 3306
    query: Select * from users.information where user_id LIKE admin


    Bytes_received =         136 -->  177
        Bytes_sent =         110 --> 8562
   Com_show_grants =           0 -->    1
   Com_show_status =           1 -->    2
           Queries =         986 -->  988
         Questions =           2 -->    4



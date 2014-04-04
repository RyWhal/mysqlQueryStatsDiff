mysqlQueryStatsDiff
===================

This script will take a given query (ex. "select * from table") and run a
"show session status" before and after that query. This script replaces
the need to dump the output of queries to a file and vimdiff.

The output of the script is the Delta between the two runs of the
"show session status command"

Usage: queryStats [-v] [-h HOST] [-d DATABASE] [-s SOCKET | --port PORT] -u USERNAME -p [-f FILTER] -q QUERY ...

Options:</br>
--help                  you're looking at it.</br>
-h --host HOSTNAME      Specify hostname [default: localhost].</br>
-d --db DATABASE        Specify database [default: mysql].</br>
-s --socket SOCKET      Specify socket.</br>
-P --port PORT          Specify port [default: 3306].</br>
-u --username USERNAME  Specify username.</br>
-p --password           Password mode.</br>
-f --filter FILTER      Specify filter.</br>
-q --query QUERY        Specify query.</br>
-v --verbose            Specify to use verbose mode</br>

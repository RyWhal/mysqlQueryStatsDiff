mysqlQueryStatsDiff
===================

This script will take a given query (ex. "select * from table") and run a
"show session status" before and after that query. This script replaces
the need to dump the output of queries to a file and vimdiff.

The output of the script is the Delta between the two runs of the
"show session status command"

Usage: queryStats [-v] [-h HOST] [-d DATABASE] [-s SOCKET | --port PORT] -u USERNAME -p [-f FILTER] -q QUERY ...

Options:
--help                  you're looking at it.
-h --host HOSTNAME      Specify hostname [default: localhost].
-d --db DATABASE        Specify database [default: mysql].
-s --socket SOCKET      Specify socket.
-P --port PORT          Specify port [default: 3306].
-u --username USERNAME  Specify username.
-p --password           Password mode.
-f --filter FILTER      Specify filter.
-q --query QUERY        Specify query.
-v --verbose            Specify to use verbose mode

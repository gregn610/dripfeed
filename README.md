<h1>dripfeed</h1>
Write out a file, one line at a time, with a ... pause

<h2>Usage</h2>
~~~
$./dripfeed.py
Usage:
  dripfeed.py [options] FILES ...
  dripfeed.py [options] -
  dripfeed.py (-h | --help)
  dripfeed.py --version
~~~

<h2>Example</h2>
~~~
$# First Terminal
$
$ seq 1000 5 1100 > ../data/test_numbers.txt
$ ./dripfeed.py -i 3 ../data/test_numbers.txt &
[1] 66929
$
[1]+  Done                    ./dripfeed.py -i 3 ../data/test_numbers.txt
~~~

and while that is running
~~~
$# Second Terminal
$ tail -f ../data/test_numbers.txt
1000
1005
1010
1015
1020
1025
1030
1035
1040
1045
1050
1055
1060
1065
1070
1075
1080
1085
1090
1095
1100
^C
$
~~~


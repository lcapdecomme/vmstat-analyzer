Démo : http://vmstat-analyzer.appspot.com/

This project is designed to help you analyze vmstat logs. 

The use case is the following:
* you're having an issue (bad response time, users complaining, or so)
* you start vmstat for some seconds during the problem (or find the values corresponding to the time when the problem happened, anyway)
** for example vmstat 3

Then, launching the jar file on command-line this way, here the typical output you should have:
$ java -jar target/vmstat-analyzer-0.1-SNAPSHOT.jar vmstat-1.txt
r  |b |avm     |fre   |re|pi|po|fr|sr|cy|in |sy    |cs   |us |sy|id|wa|pc   |ec    |
19 |1 |1668643 |24992 |0 |0 |0 |0 |0 |0 |51 |11650 |1565 |98 |2 |0 |0 |3.93 |115.7 |
22 |0 |1668185 |25443 |0 |0 |0 |0 |0 |0 |57 |11748 |1612 |98 |1 |0 |0 |3.97 |116.7 |
21 |0 |1678299 |15312 |0 |0 |0 |0 |0 |0 |82 |14731 |1735 |98 |2 |0 |0 |3.98 |117.0 |
22 |1 |1674787 |18812 |0 |0 |0 |0 |0 |0 |36 |8934  |1455 |99 |1 |0 |0 |3.98 |117.1 |
21 |1 |1672899 |20692 |0 |0 |0 |0 |0 |0 |36 |12323 |1453 |98 |2 |0 |0 |3.98 |117.1 |
17 |0 |1668602 |24978 |0 |0 |0 |0 |0 |0 |42 |15360 |1711 |97 |3 |0 |0 |3.98 |117.0 |
22 |1 |1663821 |29730 |0 |0 |0 |0 |0 |0 |36 |9430  |1635 |99 |1 |0 |0 |3.98 |117.0 |
18 |0 |1679438 |14100 |0 |0 |0 |0 |0 |0 |36 |8358  |1818 |99 |1 |0 |0 |3.94 |115.8 |
21 |1 |1678611 |14927 |0 |0 |0 |0 |0 |0 |40 |10485 |1544 |99 |1 |0 |0 |3.97 |116.9 |
15 |0 |1679784 |13749 |0 |0 |0 |0 |0 |0 |58 |12255 |1624 |98 |2 |0 |0 |3.97 |116.6 |
21 |0 |1672606 |20912 |0 |0 |0 |0 |0 |0 |81 |15712 |1793 |97 |2 |0 |0 |3.97 |116.8 |
21 |0 |1673194 |20300 |0 |0 |0 |0 |0 |0 |34 |13344 |1459 |98 |2 |0 |0 |3.98 |117.1 |
18 |1 |1659890 |33584 |0 |0 |0 |0 |0 |0 |41 |9124  |1589 |99 |1 |0 |0 |3.96 |116.4 |
22 |0 |1665145 |28324 |0 |0 |0 |0 |0 |0 |58 |6975  |1453 |99 |1 |0 |0 |3.98 |117.0 |
24 |0 |1663282 |30163 |0 |0 |0 |0 |0 |0 |51 |12276 |1789 |99 |1 |0 |0 |3.98 |116.9 |
26 |0 |1666722 |26723 |0 |0 |0 |0 |0 |0 |33 |19338 |1471 |97 |3 |0 |0 |3.98 |117.1 |
26 |1 |1662497 |30939 |0 |0 |0 |0 |0 |0 |44 |11804 |1547 |99 |1 |0 |0 |3.98 |117.0 |
29 |0 |1660061 |33370 |0 |0 |0 |0 |0 |0 |32 |6049  |1446 |99 |1 |0 |0 |3.97 |116.8 |
19 |0 |1662718 |30692 |0 |0 |0 |0 |0 |0 |31 |6749  |1483 |99 |1 |0 |0 |3.99 |117.2 |
21 |1 |1660823 |32578 |0 |0 |0 |0 |0 |0 |49 |12904 |1718 |98 |2 |0 |0 |3.98 |117.0 |

Result
WARNING: Default CPU count (4) is being used. Specify your actual number to have better results.
User space is dominating(userspace average=98.35%)
CPU-contention : a lot of threads are queued waiting for CPU. It should never be really higher than the CPU count. (r average=21.25, cpu count=4)

Note : this project is still very young (10/2011). There's room for improvement in almost every part of it.

Known limitations
-----------------
* Not very safe yet with regards to badly formated log parsing. So take care to only copy column titles and only values then.
* Lots of others, I guess :).
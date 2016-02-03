# cut_slowlog_by_timestamp
按照slowlog中timestamp提取需要的数据

该脚本:如果MySQL中slowlog文件太大，如百M、G级别查看起来较吃力，故利用timestamp，将其截取出需要数据。

mysql> select unix_timestamp('2015-10-26') as 'start_ts',unix_timestamp('2015-10-27') as 'end_ts';

+------------+------------+
| start_ts   | end_ts     |
+------------+------------+
| 1445788800 | 1445875200 |
+------------+------------+

python pyslow.py path/slow_log.log start_ts end_ts

python pyslow.py /tmp/slow.log 1445788800 1445875200

若有更好的方法，望朋友能分享，谢谢!

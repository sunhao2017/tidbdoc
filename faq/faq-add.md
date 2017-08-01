## 如何备份恢复
首先 TIDB 本身就是高可用构架，每条数据都有两个副本（加自己是三个）。所以如果不是非常需要备份的场景是完全 ok 的。 另一方面，我们高度兼容 MYSQL ，所以你可以直接使用 MYSQL 的备份恢复工具例如 mydumper myloader。我们也推荐使用我们的 loader 工具进行备份。

tidb 有自身的 binlog，可以做数据增量备份 同时每天可以用 mydumper 做一份全量，结合 tidb-binlog 就可以恢复到任意时间点的状态
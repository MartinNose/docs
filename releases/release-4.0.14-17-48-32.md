---
title: TiDB 4.0.14 Release Notes
category: Releases
---



# TiDB 4.0.14 Release Notes

Release Date: July 22, 2021

TiDB version: 4.0.14

## __unsorted

+ PingCAP/TiDB

    - fix range building for binary literal [#26455](https://github.com/pingcap/tidb/pull/26455)
    - Fix copt-cache metrics, it will display the number of  hits/miss/evict on Grafana. [#26342](https://github.com/pingcap/tidb/pull/26342)
    - Change the lock record into put record for the index keys using point/batch point get for update read. [#26223](https://github.com/pingcap/tidb/pull/26223)
    - load: fix load data with non-utf8 can succeed [#26142](https://github.com/pingcap/tidb/pull/26142)
    - TiDB now supports the mysql system variable init_connect and associated functionality. [#26031](https://github.com/pingcap/tidb/pull/26031)
    - planner: support stable result mode [#26013](https://github.com/pingcap/tidb/pull/26013)
    - planner: support stable result mode [#26003](https://github.com/pingcap/tidb/pull/26003)
    -  [#25904](https://github.com/pingcap/tidb/pull/25904)
    - Enlarge the variable tidb_stmt_summary_max_stmt_count default value from 200 to 3000 [#25872](https://github.com/pingcap/tidb/pull/25872)
    - Enable the pushdown of builtin function json_unquote() to TiKV. [#25721](https://github.com/pingcap/tidb/pull/25721)
    - planner: select distinct should bypass batchget [#25532](https://github.com/pingcap/tidb/pull/25532)
    - Important security issue for handling ALTER USER statements [#25347](https://github.com/pingcap/tidb/pull/25347)
    - Fix the bug that TIKV_REGION_PEERS table did not have the correct DOWN status. [#24918](https://github.com/pingcap/tidb/pull/24918)
    - Handle a potential statistic object's memory leak when HTTP api is used [#24650](https://github.com/pingcap/tidb/pull/24650)
    - don't let SPM be affected by charset [#23295](https://github.com/pingcap/tidb/pull/23295)
    - time: parse datatime won't truncate the reluctant string. [#22260](https://github.com/pingcap/tidb/pull/22260)
    - fix a bug that select into outfile has no data with year column type  [#22185](https://github.com/pingcap/tidb/pull/22185)


+ TiKV/TiKV

    - Fix duration calculation panics on certain platforms [#10572](https://github.com/tikv/tikv/pull/10572)
    - Fix duration calculation panics on certain platforms [#10566](https://github.com/tikv/tikv/pull/10566)
    - fix wrong function cast double to double [#10532](https://github.com/tikv/tikv/pull/10532)
    - Ensure panic output is flushed to the log [#10488](https://github.com/tikv/tikv/pull/10488)
    - - fix follower meta corruption in rare cases with more than 4 replicas [#10484](https://github.com/tikv/tikv/pull/10484)
    - Avoid panic when building a snapshot twice if encryption enabled [#10462](https://github.com/tikv/tikv/pull/10462)
    - copr: fix the wrong arguments type of json_unquote [#10425](https://github.com/tikv/tikv/pull/10425)
    - skip clearing callback during gracefully shutdown to avoid breaking ACID in some cases [#10395](https://github.com/tikv/tikv/pull/10395)
    - ```release-note [#10360](https://github.com/tikv/tikv/pull/10360)
    - Fix OOM when TiCDC resumes a changefeed in a cluster that has lots of regions being captured. [#10320](https://github.com/tikv/tikv/pull/10320)
    - ```release-note [#10288](https://github.com/tikv/tikv/pull/10288)
    - Approximate split range evenly [#10275](https://github.com/tikv/tikv/pull/10275)
    - BR now supports S3-compatible storage using virtual-host addressing style. [#10242](https://github.com/tikv/tikv/pull/10242)
    - Limit CDC sink memory consumption. [#10147](https://github.com/tikv/tikv/pull/10147)
    - Add metrics to see pending pd heartbeats number [#10008](https://github.com/tikv/tikv/pull/10008)
    - Change the default merge-check-tick-interval to 2 to speed up the retry of merge process [#9676](https://github.com/tikv/tikv/pull/9676)
    - Fix an issue that split may panic and corrupt the metadata if the split process is too slow and region merge is open. [#9584](https://github.com/tikv/tikv/pull/9584)


+ PingCAP/PD

    - TiDB Dashboard: Add OIDC based SSO support [#3882](https://github.com/tikv/pd/pull/3882)
    - ```release-note [#3858](https://github.com/tikv/pd/pull/3858)
    - ```release-note [#3854](https://github.com/tikv/pd/pull/3854)
    - ```release-note [#3825](https://github.com/tikv/pd/pull/3825)
    - ```release-note [#3797](https://github.com/tikv/pd/pull/3797)
    - ```release-note [#3790](https://github.com/tikv/pd/pull/3790)
    - ```release-note [#3773](https://github.com/tikv/pd/pull/3773)
    - ```release-note [#3761](https://github.com/tikv/pd/pull/3761)
    - ```release-note [#3718](https://github.com/tikv/pd/pull/3718)
    - ```release-note [#3703](https://github.com/tikv/pd/pull/3703)
    - ```release-note [#3680](https://github.com/tikv/pd/pull/3680)


+ Tools

    + PingCAP/TiCDC

        - puller,mounter,processor: always pull the old value internally [#2304](https://github.com/pingcap/ticdc/pull/2304)
        - Fix extra partition dispatching when adding new table partition. [#2205](https://github.com/pingcap/ticdc/pull/2205)
        - Better err msg when PD endpoint missing certificate [#2184](https://github.com/pingcap/ticdc/pull/2184)
        - Add capture-session-ttl in cdc server config [#2169](https://github.com/pingcap/ticdc/pull/2169)
        - Fix a bug that could cause cdc server panic because of the late calculation of resolved ts [#2046](https://github.com/pingcap/ticdc/pull/2046)
        - Fix panic when TiCDC fails to read /proc/meminfo [#2023](https://github.com/pingcap/ticdc/pull/2023)
        - Reduce unnecessary memory consumption [#2011](https://github.com/pingcap/ticdc/pull/2011)
        - Make sorter IO errors more user-friendly. [#1976](https://github.com/pingcap/ticdc/pull/1976)
        - Fix Unified Sorter memory consumption when tables are many. [#1957](https://github.com/pingcap/ticdc/pull/1957)
        - Decrease the default gRPC connection pool size to decrease goroutines count. [#1950](https://github.com/pingcap/ticdc/pull/1950)
        - Fix a bug that some MySQL connection could leak after MySQL sink meets error and pauses. [#1945](https://github.com/pingcap/ticdc/pull/1945)
        - Add concurrency limit to the region incremental scan in kv client. [#1930](https://github.com/pingcap/ticdc/pull/1930)
        - Add concurrency limit to the region incremental scan in kv client. [#1926](https://github.com/pingcap/ticdc/pull/1926)
        - Add metrics for table memory consumption [#1884](https://github.com/pingcap/ticdc/pull/1884)
        - Reduce memory malloc in sort heap to avoid too much CPU overhead. [#1862](https://github.com/pingcap/ticdc/pull/1862)


## Bug Fixes

+ PingCAP/TiDB

    - Fix the problem that the div function may lose precision when it's a subpart of the whole expression. [#26390](https://github.com/pingcap/tidb/pull/26390)
    - Generate correct number of rows when all agg funcs are pruned [#26039](https://github.com/pingcap/tidb/pull/26039)
    - executor: fix ifnull bug when arg is enum/set [#26035](https://github.com/pingcap/tidb/pull/26035)
    - fix wrong aggregate pruning for some cases [#26033](https://github.com/pingcap/tidb/pull/26033)
    - Fix incorrect result of set type for merge join  [#26032](https://github.com/pingcap/tidb/pull/26032)
    - expression: fix IN expr critical bug [#25665](https://github.com/pingcap/tidb/pull/25665)
    - Fix panic when 'select ... for update' works on a join operation and the join uses partition table [#25501](https://github.com/pingcap/tidb/pull/25501)
    - Fix the issue point get cached plan of prepared statement is incorrectly used by in transaction point get statement. [#24764](https://github.com/pingcap/tidb/pull/24764)


## Compatibility Changes

+ PingCAP/TiDB

    - For users upgrading from TiDB 4.0, the value of tidb_multi_statement_mode is now OFF. It is recommended to use the multi-statement feature of your client library instead, see the documentation on tidb_multi_statement_mode for additional details. [#25749](https://github.com/pingcap/tidb/pull/25749)



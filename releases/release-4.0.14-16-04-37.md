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


+ TiKV/TiKV

    - - fix follower meta corruption in rare cases with more than 4 replicas [#10484](https://github.com/tikv/tikv/pull/10484)


+ Tools

    + PingCAP/TiCDC

        - puller,mounter,processor: always pull the old value internally [#2304](https://github.com/pingcap/ticdc/pull/2304)



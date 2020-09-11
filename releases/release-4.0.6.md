---
title: TiDB 4.0.6 Release Notes
---

# TiDB 4.0.6 Release Notes

Release date: September 9, 2020

TiDB version: 4.0.6

## Improvements

+ TiDB

    - Replace error code and message with standard error [#19888](https://github.com/pingcap/tidb/pull/19888)
    - Improve the write performance of partition table [#19649](https://github.com/pingcap/tidb/pull/19649)
    - Record more RPC runtime information in cop runtime stats [#19264](https://github.com/pingcap/tidb/pull/19264)
    - Forbidden creating table in metrics_schema and performance_schema [#19792](https://github.com/pingcap/tidb/pull/19792)
    - Support adjust the concurrency on union executor [#19886](https://github.com/pingcap/tidb/pull/19886)
    - Support out join in broadcast join [#19664](https://github.com/pingcap/tidb/pull/19664)

+ PD

    - Dashboard: update to v2020.09.08.1 [#2928](https://github.com/pingcap/pd/pull/2928)
    - metrics: add more metrics for region and store heartbeat [#2891](https://github.com/tikv/pd/pull/2891)
    - Change back to the original way to control the low space threshold [#2875](https://github.com/pingcap/pd/pull/2875)
    - Support standard error code [#2918](https://github.com/tikv/pd/pull/2918) [#2911](https://github.com/tikv/pd/pull/2911) [#2913](https://github.com/tikv/pd/pull/2913) [#2915](https://github.com/tikv/pd/pull/2915) [#2912](https://github.com/tikv/pd/pull/2912) [#2907](https://github.com/tikv/pd/pull/2907) [#2906](https://github.com/tikv/pd/pull/2906) [#2903](https://github.com/tikv/pd/pull/2903) [#2806](https://github.com/tikv/pd/pull/2806) [#2900](https://github.com/tikv/pd/pull/2900) [#2902](https://github.com/tikv/pd/pull/2902)

+ TiFlash

    - Add some metrics about apply Region snapshots and ingest SST files [#1088](https://github.com/pingcap/tics/pull/1088)
    - Fix the problem that CN check doesn't work on https_port and metrics_port [#1064](https://github.com/pingcap/tics/pull/1064)## Bug Fixes

## Bug Fixes

+ TiDB

    - Fix an issue of tikv_cop_wait time in metric profile [#19881](https://github.com/pingcap/tidb/pull/19881)
    - Fix the wrong result of `SHOW GRANTS` [#19834](https://github.com/pingcap/tidb/pull/19834)
    - Fix the incorrect query result for `!= ALL (subq)` [#19831](https://github.com/pingcap/tidb/pull/19831)
    - Fix a bug of converting enum and set [#19778](https://github.com/pingcap/tidb/pull/19778)
    - Add a privilege check for `SHOW STATS_META`, `SHOW STATS_BUCKET` [#19760](https://github.com/pingcap/tidb/pull/19760)
    - Fix unmatched column lengths errors caused by `builtinGreatestStringSig` and `builtinLeastStringSig` [#19758](https://github.com/pingcap/tidb/pull/19758)
    - Fallback vectorize control expressions [#19749](https://github.com/pingcap/tidb/pull/19749)
    - Fix errors in `Apply` when the type of correlation column is `Bit` [#19692](https://github.com/pingcap/tidb/pull/19692)
    - Fix an issue of query processlist and cluster_log bug in mysql8 client [#19690](https://github.com/pingcap/tidb/pull/19690)
    - Fix an issue of same type plans with different plan digest [#19684](https://github.com/pingcap/tidb/pull/19684)
    - Forbidden changing `Decimal` to `Int` [#19682](https://github.com/pingcap/tidb/pull/19682)
    - Fix an issue that `SELECT ... INTO OUTFILE` returns runtime error [#19672](https://github.com/pingcap/tidb/pull/19672)
    - Fix an incorrect implementation in `builtinRealIsFalseSig` [#19670](https://github.com/pingcap/tidb/pull/19670)
    - Fix partition expression check missing the parentheses expression [#19614](https://github.com/pingcap/tidb/pull/19614)
    - Fix a query error when there is an `Apply` upon `HashJoin` [#19611](https://github.com/pingcap/tidb/pull/19611)
    - Fix an incorrect result of vectorized casting `Real` as `Time` [#19594](https://github.com/pingcap/tidb/pull/19594)
    - Fix `SHOW GRANTS` can show grants for not existed user [#19588](https://github.com/pingcap/tidb/pull/19588)
    - Fix a query error when there is an `Apply` upon `IndexLookupJoin` [#19566](https://github.com/pingcap/tidb/pull/19566)
    - Fix wrong results when convert `Apply` to `HashJoin` on partition table [#19546](https://github.com/pingcap/tidb/pull/19546)
    - Fix incorrect results when there is an `IndexLookUp` under the inner side of an `Apply` [#19508](https://github.com/pingcap/tidb/pull/19508)
    - Fix a unexpected panic when using view [#19491](https://github.com/pingcap/tidb/pull/19491)
    - Fix an incorrect result of `anti-semi-join` query [#19477](https://github.com/pingcap/tidb/pull/19477)
    - Fix dropping stats should delete topN [#19465](https://github.com/pingcap/tidb/pull/19465)
    - Fix a wrong result caused by mistaken usage of batch point get [#19460](https://github.com/pingcap/tidb/pull/19460)
    - Fix a bug that it can't find column in `indexLookupJoin` with virtual generated column [#19439](https://github.com/pingcap/tidb/pull/19439)
    - Fix different plans between select and update query [#19403](https://github.com/pingcap/tidb/pull/19403)
    - Fix a data race for tiflash work index in region cache [#19362](https://github.com/pingcap/tidb/pull/19362)
    - Fix logarithm functions [#19291](https://github.com/pingcap/tidb/pull/19291)
    - Fix a unexpected error when TiDB spilling to disk [#19272](https://github.com/pingcap/tidb/pull/19272)
    - Make single partition table support index join on the inner side [#19197](https://github.com/pingcap/tidb/pull/19197)
    - Fix the wrong hash key for decimal [#19188](https://github.com/pingcap/tidb/pull/19188)
    - Fix an issue that TiDB will raise no-regions error when table endKey and region endKey are same [#19895](https://github.com/pingcap/tidb/pull/19895)
    - Fix an issue that unexpect sucess to alter partition [#19891](https://github.com/pingcap/tidb/pull/19891)
    - Fix a wrong default max allowed packet for push downed expression [#19876](https://github.com/pingcap/tidb/pull/19876)
    - Fix a wrong behavior for `Max/Min` on `ENUM/SET` column [#19869](https://github.com/pingcap/tidb/pull/19869)
    - Fix read failure from system tables `tiflash_segments` and `tiflash_tables` when some tiflash node is down [#19748](https://github.com/pingcap/tidb/pull/19748)
    - Fix a wrong result for aggregation `Count(col)` [#19628](https://github.com/pingcap/tidb/pull/19628)
    - Fix a runtime error in `TRUNCATE` [#19445](https://github.com/pingcap/tidb/pull/19445)
    - Fix `PREPARE` statement FROM `@Var` will fail when `Var` contains uppercase characters [#19378](https://github.com/pingcap/tidb/pull/19378)
    - Fix a bug that schema charset modification in an uppercase schema will cause panic [#19302](https://github.com/pingcap/tidb/pull/19302)
    - Fix a inconsistence of plan between `information_schema.statements_summary` and `explain`, which contains tikv/tiflash info [#19159](https://github.com/pingcap/tidb/pull/19159)
    - Fix the file exists errors in tests for `select into outfile` [#19725](https://github.com/pingcap/tidb/pull/19725)

+ TiFlash

    - Fix the issue that TiFlash throw exceptions after modifying column nullable attribute [#1081](https://github.com/pingcap/tics/pull/1081)
    - Fix the issue that after renaming the primary key column in previous versions, TiFlash may not start after upgrading to v4.0.4/v4.0.5 [#1072](https://github.com/pingcap/tics/pull/1072)
    - Fix wrong result of FROM_UNIXTIME when input is NULL [#1047](https://github.com/pingcap/tics/pull/1047)
    - Fix the issue that TiFlash is not available after users applied unsupported column data type modifications [#1009](https://github.com/pingcap/tics/pull/1009)

## Others

+ TiDB

    - Add sql digest for process list [#19829](https://github.com/pingcap/tidb/pull/19829)
    - Switch to pessimistic txn mode for autocommit statement retry [#19796](https://github.com/pingcap/tidb/pull/19796)
    - Support `%r`, `%T` data format in `Str_to_date()` [#19693](https://github.com/pingcap/tidb/pull/19693)
    - Make `SELECT INTO OUTFILE` require the file privilege [#19577](https://github.com/pingcap/tidb/pull/19577)
    - Support stddev_pop function [#19541](https://github.com/pingcap/tidb/pull/19541)
    - Make DDL avoid taking too long in retry [#19488](https://github.com/pingcap/tidb/pull/19488)
    - Make statements like `alter table db.t1 add constraint fk foreign key (c2) references t2(c1)` execute without first executing `use db` [#19471](https://github.com/pingcap/tidb/pull/19471)
    - Fix `INFORMATION_SCHEMA.CLUSTER_HARDWARE` does not have raid devices information [#19457](https://github.com/pingcap/tidb/pull/19457)
    - Make dispatch errors be changed from an Error to an Info message in the server log file [#19454](https://github.com/pingcap/tidb/pull/19454)
    - Add `TiDB-Runtime` dashboard [#19396](https://github.com/pingcap/tidb/pull/19396)
    - Make add index can exit on generated column with `case-when` expression parse error [#19395](https://github.com/pingcap/tidb/pull/19395)
    - Improve compatibility for ALTER TABLE algorithms [#19364](https://github.com/pingcap/tidb/pull/19364)
    - Encode insert/delete/update plan in slow log plan field [#19269](https://github.com/pingcap/tidb/pull/19269)

+ TiKV

    - Optimize QPS drop when doing UnsafeDestroyRange [#8627](https://github.com/tikv/tikv/pull/8627)
    - Fix the estimation error for a non-index column with collation enabled. [#8620](https://github.com/tikv/tikv/pull/8620)
    - Error-code: support to generate metafile [#8619](https://github.com/tikv/tikv/pull/8619)
    - Add perf statistics for cf scan detail [#8618](https://github.com/tikv/tikv/pull/8618)
    - Fix the deadlock between the PD client thread and other threads calling PD sync requests. [#8612](https://github.com/tikv/tikv/pull/8612)
    - Fix a panic issue if a TiKV runs very slow during conf change. [#8497](https://github.com/tikv/tikv/pull/8497)
    - Add perf context panel for grafana template [#8467](https://github.com/tikv/tikv/pull/8467)
    - Update jemalloc to 5.2.1 [#8463](https://github.com/tikv/tikv/pull/8463)
    - Fix the issue that green GC may miss locks during transferring regions. [#8460](https://github.com/tikv/tikv/pull/8460)
    - Support float CPU quota in cgroup. [#8427](https://github.com/tikv/tikv/pull/8427)

+ PD

    - Add `initial-cluster-token` configuration to avoid different clusters communicate during bootstrap [#2922](https://github.com/pingcap/pd/pull/2922)
    - Fix the unit of store limit rate when the mode is auto [#2826](https://github.com/pingcap/pd/pull/2826)
    - Fix the issue that some scheduler persist config without solving error [#2818](https://github.com/tikv/pd/pull/2818)
    - fix empty http response in scheduler [#2871](https://github.com/tikv/pd/pull/2871) [#2874](https://github.com/tikv/pd/pull/2874)

+ TiFlash

    - `Do not optimize applying snapshot by multi-thread when raftstore.snap-handle-pool-size is 0` [#1086](https://github.com/pingcap/tics/pull/1086)
    - `Fix bug causes segment fault while computing table sync status` [#1077](https://github.com/pingcap/tics/pull/1077)
    - For invalid collation, treated as `utf8mb4_bin` in TiFlash [#1069](https://github.com/pingcap/tics/pull/1069)
    - Added some Grafana panels about write stall, and added some settings to avoid write stall. [#1051](https://github.com/pingcap/tics/pull/1051)

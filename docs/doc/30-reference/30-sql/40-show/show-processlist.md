---
title: SHOW PROCESSLIST
---

The Databend process list indicates the operations currently being performed by the set of threads executing within the server.

The SHOW PROCESSLIST statement is one source of process information.

## Syntax

```
SHOW PROCESSLIST
```

## Examples

```sql
SHOW PROCESSLIST;
+--------------------------------------+-------+-----------------+------+-------+----------+--------------------------------------------------------------------------------------+--------------+------------------------+-------------------------+-------------------------+--------------------------+
| id                                   | type  | host            | user | state | database | extra_info                                                                           | memory_usage | dal_metrics_read_bytes | dal_metrics_write_bytes | scan_progress_read_rows | scan_progress_read_bytes |
+--------------------------------------+-------+-----------------+------+-------+----------+--------------------------------------------------------------------------------------+--------------+------------------------+-------------------------+-------------------------+--------------------------+
| 579eca1f-13d2-401b-9fb9-e879c10d25dd | MySQL | 127.0.0.1:55551 | root | Query | default  | SELECT sum(number) from numbers_mt(10000000000) group by number%3, number%4,number%5 | 0.00 B       | 0.00 B                 | 0.00 B                  |               348050000 | 2.59 GiB                 |
| 49a322bc-136d-4085-b83b-28a1c9ba2450 | MySQL | 127.0.0.1:55501 | root | Query | default  | show processlist                                                                     | 0.00 B       | 0.00 B                 | 0.00 B                  |                       0 | 0.00 B                   |
+--------------------------------------+-------+-----------------+------+-------+----------+--------------------------------------------------------------------------------------+--------------+------------------------+-------------------------+-------------------------+--------------------------+
```

# Alex's Linux Setup

> [!WARNING]
> This is not production-ready, do not use yet but feel free to take inspiration.

# Setup

## Partitioning

### Boot

| Mount Point | Size | Name | Mount Options |
| ----------- | ---- | ---- | ------------- |
| `/boot`     | 1G   | N/A  | N/A           |

### vg_main

| Mount Point | Size | Name       | Mount Options |
| ----------- | ---- | ---------- | ------------- |
| `swap`      | 8G   | lv_swap    | N/A           |
| `/`         | 30G  | lv_root    | N/A           |
| `/usr`      | 20G  | lv_usr     | N/A           |
| `/home`     | 50G  | lv_home    | N/A           |
| `/tmp`      | 5G   | lv_tmp     | `noexec`      |
| `/var`      | 20G  | lv_var     | N/A           |
| `/var/log`  | 10G  | lv_var_log | N/A           |
| `/var/tmp`  | 5G   | lv_var_tmp | `noexec`      |

### vg_data

Creating a separate volume group for data in places such as `/srv` isn't very common,
or not in any tutorials that I have seen. There's often debate on when it's appropriate
to separate data into separate volume groups. Whilst not strictly necessary, it may prove
useful to place *potentially* fragile, important and/or publically-consumed data within
its own volume group for both security (isolation) and redundancy (creating snapshots
without including system data).

> [!NOTE]
> The table below shows how you might organise `vg_data` - there are no rules for this.

| Mount Point      | Size | Name      | Mount Options |
| ---------------- | ---- | --------- | ------------- |
| `/srv`           | 30G  | lv_srv    | N/A           |
| `/srv/db`        | 50G  | lv_srv_db | N/A           |
| `/srv/minecraft` | 20G  | lv_srv_mc | N/A           |

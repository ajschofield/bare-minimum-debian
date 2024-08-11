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
| `/var/tmp`  | 5G   | lv_var_tmp | N/A           |

### vg_data


| Mount Point | Size | Name   | Mount Options |
| ----------- | ---- | ------ | ------------- |
| `/srv`      | 30G  | lv_srv | N/A           |
| `/srv/      |

# 替换DB2安装包
路径：
`ansible-db2/files/v11.1_linuxx64_server_t.tar.gz`

# 修改目标主机ID
`vim hosts`
```ini
[db2]
10.20.10.20  ansible_user=root ansible_password=123456
```

# 启动
ansible-playbook -i hosts playbook_install_db2.yml

# 安装成功提示
```bash
TASK [ansible-db2 : Validate results] *********************************************************************************ok: [10.20.10.20] => {
    "db2_val": {                                                                                                               "changed": false,                                                                                                      "cmd": [                                                                                                                   "/opt/ibm/db2/V11.1/bin/db2val",                                                                                       "-o"                                                                                                               ],                                                                                                                     "delta": "0:01:38.362501",                                                                                             "end": "2019-07-06 20:12:57.082953",                                                                                   "failed": false,                                                                                                       "failed_when_result": false,                                                                                           "rc": 0,                                                                                                               "start": "2019-07-06 20:11:18.720452",                                                                                 "stderr": "",                                                                                                          "stderr_lines": [],                                                                                                    "stdout": "DBI1379I  db2val 命令正在运行。这可能要花几分钟才能完成。\n\nDBI1335I  验证安装在 /opt/ibm/db2/V11.1 处的 DB2 副本的安装文件成功。\n\nDBI1343I  成功完成了 db2val 命令。有关详细信息，请参阅日志文件 /tmp/db2val-190706_201118.log。",
        "stdout_lines": [                                                                                                          "DBI1379I  db2val 命令正在运行。这可能要花几分钟才能完成。",                                                           "",                                                                                                                    "DBI1335I  验证安装在 /opt/ibm/db2/V11.1 处的 DB2 副本的安装文件成功。",                                               "",                                                                                                                    "DBI1343I  成功完成了 db2val 命令。有关详细信息，请参阅日志文件 /tmp/db2val-190706_201118.log。"                   ]                                                                                                                  }                                                                                                                  }                                                                                                                      
TASK [ansible-db2 : Create Databases] *********************************************************************************skipping: [10.20.10.20]

TASK [ansible-db2 : Create Database Log] ******************************************************************************skipping: [10.20.10.20]

PLAY RECAP ************************************************************************************************************10.20.10.20                : ok=20   changed=11   unreachable=0    failed=0     
```

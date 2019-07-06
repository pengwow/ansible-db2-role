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


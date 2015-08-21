# playbook実行環境

Vagrant + CentOS7.1 + ansible v1.9.2 で正常動作している事を確認しています。

# redmineの環境

* CentOS: v7.x
* ruby: v2.1
* rbenv: latest
* apache: v2.4(event mpm)
* mariadb latest
* redmine v2.6 or v3.0 or v3.1

# インベントリ

ansible-playbook-redmine/inventry

```ini
[redmine]
192.168.33.21

[redmine:vars]
ansible_ssh_port=22
ansible_ssh_user=vagrant
ansible_ssh_pass=vagrant
```

[redmine]の部分を任意のIPに変更して下さい。

# 実行方法

```
./playbook.sh
```

# インストールするredmineのバージョン

以下よりインストールするバージョンを指定する事ができます。  
ansible-playbook-redmine/group_vars/common.yml

## ver3.1をインストールする場合

common.yml の redmine_svn_branches_url を以下のように設定して下さい。
```yaml
redmine_svn_branches_url: http://svn.redmine.org/redmine/branches/3.1-stable
```

# redmineのログインID/PASS

ログイン: admin  
パスワード: admin  

http://redmine.jp/tech_note/first-step/admin/login/

# このplaybookのインストール手順の参考

http://blog.redmine.jp/articles/3_1/installation_centos/  
公式サイトを参考に、playbook化してみました。
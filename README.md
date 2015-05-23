# playbook実行環境

Vagrant + CentOS7.1 + ansible v1.9.1 で正常動作している事を確認しています。

# redmineの環境

* CentOS: v7.x
* ruby: v2.1
* rbenv: latest
* apache: v2.4(event mpm)
* mariadb latest
* redmine v2.6 or v3.0

# インベントリ

ansible-playbook-redmine/development

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
ansible-playbook -i development site.yml
```

# インストールするredmineのバージョン

以下よりインストールするバージョンを指定する事ができます。
ansible-playbook-redmine/group_vars/common.yml

## ver2.6をインストールする場合

common.yml の redmine_svn_branches_url を以下のように設定して下さい。
```yaml
redmine_svn_branches_url: http://svn.redmine.org/redmine/branches/2.6-stable
```

※ デフォルトで2.6が指定されています。

## ver3.0をインストールする場合

common.yml の redmine_svn_branches_url を以下のように設定して下さい。
```yaml
redmine_svn_branches_url: http://svn.redmine.org/redmine/branches/3.0-stable
```

# このplaybookのインストール手順の参考

http://blog.redmine.jp/articles/3_0/installation_centos/
公式サイトを参考に、playbook化してみました。
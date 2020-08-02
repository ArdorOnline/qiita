# useradd コマンド
ユーザの追加は、一般ユーザでは行えない。
管理者権限を持つアカウントで操作する。

任意のユーザ名でユーザを追加するコマンドは次の通り。

```
# useradd [オプション] username
```

```man
useradd [-c comment] [-d home_dir]
        [-e expire_date] [-f inactive_time]
        [-g initial_group] [-G group[,...]]
        [-m [-k skeleton_dir]] [-o] [-p passwd]
        [-s shell] [-u uid] login
```

## オプション
| オプション                      | 説明 |
|:--                             |:--|
|  -b, --base-dir BASE_DIR       |新アカウントのホームディクトリのベースディレクトリ|
|  -c, --comment COMMENT         |新アカウントの GECOS フィールド|
|  -d, --home-dir HOME_DIR       |新アカウントのホームディレクトリ|
|  -D, --defaults                |useradd のデフォルト設定を表示または変更|
|  -e, --expiredate EXPIRE_DATE  |新アカウントの期限切れ日付|
|  -f, --inactive INACTIVE       |新アカウントのパスワード無効化日数|
|  -g, --gid GROUP               |新アカウントの主グループの名前または ID|
|  -G, --groups GROUPS           |新アカウントの補助グループのリスト|
|  -h, --help                    |このヘルプを表示して終了する|
|  -k, --skel SKEL_DIR           |雛型ディレクトリに指定のものを使う|
|  -K, --key KEY=VALUE           |/etc/login.defs のデフォルトより優先される|
|  -l, --no-log-init             |ユーザを lastlog, faillog のデータベースに追加しない|
|  -m, --create-home             |ユーザのホームディレクトリを作成する|
|  -M, --no-create-home          |ユーザのホームディレクトリを作成しない|
|  -N, --no-user-group           |ユーザと同名のグループを作成しない|
|  -o, --non-unique              |UID が同じユーザの作成を許す|
|  -p, --password PASSWORD       |新アカウントの暗号化されたパスワード|
|  -r, --system                  |システムアカウントを作成します|
|  -R, --root CHROOT_DIR         |chroot するディレクトリ|
|  -s, --shell SHELL             |新アカウントのログインシェル|
|  -u, --iud UID                 |新アカウントのユーザ ID|
|  -U, --user-group              |ユーザと同じ名前のグループを作成する|
|  -Z, --selinux-user SEUSER     |SELinux のユーザマッピングに指定したSEUSER を使う|

## デフォルト値の変更
-D オプションを指定すると、 useradd は現在のデフォルト値を表示するか、
またはオプションで与えられた値に応じて、デフォルト値を変更する。使用可能なオプションは次の通り。

```
# useradd -D [オプション]
```

```man
useradd -D [-g default_group] [-b default_home]
           [-e default_expire_date] [-f default_inactive]
           [-s default_shell]
```

| オプション                      | 説明 |
|:--                             |:--|
| -b,  --base-dir                | デフォルトのホームディレクトリを指定|
| -e,  --expiredate              | デフォルトのアカウントが無効になる日数を指定|
| -f,  --inactive                | デフォルトのパスワードの仕様期限が切れてから使用不能になるまでの日数を指定|
| -g,  --gid                     | ユーザの初期グループを指定|
| -s,  --shell                   | ユーザのログインシェルを指定|

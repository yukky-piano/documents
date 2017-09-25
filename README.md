# ssh
* sshの鍵作成
```
$ cd ~
$ mkdir .ssh
$ cd .ssh
$ ssh-keygen -t  rsa
```
* sshを登録
```
$ pbcopy < ~/.ssh/id_rsa.pub (Mac)
$ clip < ~/.ssh/id_rsa.pub (Windows)
```

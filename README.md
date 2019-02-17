# GCPメモ
## google cloud strageのマウント
### インストール (Ubuntu16.04)
```
export GCSFUSE_REPO=gcsfuse-`lsb_release -c -s`
echo "deb http://packages.cloud.google.com/apt $GCSFUSE_REPO main" | sudo tee /etc/apt/sources.list.d/gcsfuse.list
curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
sudo apt update
sudo apt install gcsfuse
```
### マウント
```
sudo gcsfuse -o allow_other --uid $(id -u $USER) -gid $(id -g $USER)  バケット名 マウントパス
```

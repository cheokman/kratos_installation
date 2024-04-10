# Kratos Bootstrap

## Linux Bootstrap

Create Development Software Engineer(swe) Account in Linux

Login as root

Add swe user and set password

```bash
useradd swe
passwd swe
```

create working director /opt/workspace

```bash
mkdir -p /opt/workspace
chown swe.swe -R /opt
```

install wget

```bash
yum install wget #CentOS
apt install wget #Ubuntu
```

change to swe user

```bash
su - swe
```

## Golang Bootstrap (using swe user)

Install Golang in /opt/workspace/lib/go

```bash 
mkdir -p /opt/workspace/lib/pkg
mkdir -p /opt/workspace/lib/go
mkdir -p /opt/workspace/src/golang

wget -O /opt/workspace/lib/pkg/go1.22.1.linux-amd64.tar.gz https://go.dev/dl/go1.22.1.linux-amd64.tar.gz
mkdir -p /opt/workspace/lib/go/go1.22.1
tar zxvf /opt/workspace/lib/pkg/go1.22.1.linux-amd64.tar.gz -C /opt/workspace/lib/go/go1.22.1 --strip-components=1
ln -s /opt/workspace/lib/go/go1.22.1 /opt/workspace/lib/go/current

mkdir -p /opt/workspace/golang/src
echo 'export GOROOT=/opt/workspace/lib/go/current' >> $HOME/.bashrc
echo 'export GOPATH=/opt/workspace/golang' >> $HOME/.bashrc
echo 'export PATH=$PATH:$GOROOT/bin:$GOPATH/bin' >> $HOME/.bashrc
```


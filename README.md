# couchbase_toy
couchbase 를 이용한 toy project (/w python client sdk)

 ##couchbase-python-client:2.10 설치

## pre-install

### centos8 에서 설치
### pre-request 
pre-install
option)
- ln -s /usr/bin/python3 /usr/bin/python
- ln -s /usr/bin/pip3 /usr/bin/pip

mendentoy
- yum install -y python36-devel gcc libev libuv



libcouchbase  install
- wget https://github.com/couchbase/libcouchbase/releases/download/2.10.6/libcouchbase-2.10.6_centos8_x86_64.tar

tar 해제 후
sudo)
rpm -ivh libcouchbase2-core-2.10.6-1.el8.x86_64.rpm
rpm -ivh libcouchbase-devel-2.10.6-1.el8.x86_64.rpm
rpm -ivh libcouchbase2-libev-2.10.6-1.el8.x86_64.rpm
rpm -ivh libcouchbase2-libevent-2.10.6-1.el8.x86_64.rpm

git clone http://github.com/couchbase/couchbase-python-client
cd couchbase-python-client
git checkout -b release25 remotes/origin/release25

sudo)
python setup.py build_ext --inplace
export PYCBC_BUILD=DISTUTILS
pip install .

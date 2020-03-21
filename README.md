# couchbase_toy
couchbase 를 이용한 toy project (/w python client sdk)

 ##couchbase-python-client:2.10 설치

## pre-install

### centos8 에서 설치
### pre-request 
 - sudo yum install python36-devel (python3.6 or higher)
 - yum install gcc
 - yum install libev
 - yum install libuv
 
 libcouchbase install ( ref: https://github.com/couchbase/couchbase-python-client/blob/release25/README.rst#prerequisites)
 - downlaod : wget https://github.com/couchbase/libcouchbase/releases/download/2.10.6/libcouchbase-2.10.6_centos8_x86_64.tarhttps://github.com/couchbase/libcouchbase/releases
 - install 
   -. rpm -ivh libcouchbase-devel-2.10.6-1.el8.x86_64.rpm
   -. rpm -ivh libcouchbase2-core-2.10.6-1.el8.x86_64.rpm
   -. rpm -ivh libcouchbase-devel-2.10.6-1.el8.x86_64.rpm
   -. rpm -ivh libcouchbase2-libev-2.10.6-1.el8.x86_64.rpm
   -. rpm -ivh libcouchbase2-libevent-2.10.6-1.el8.x86_64.rpm

 - 설치 확인
   [root@localhost /]# ls -al /usr/lib64/libcouchbase.so
   lrwxrwxrwx. 1 root root 17 Feb 26 13:07 /usr/lib64/libcouchbase.so -> libcouchbase.so.2

### python clicent sdk 설치
   reference page: https://github.com/couchbase/libcouchbase
   https://github.com/couchbase/couchbase-python-client/blob/release25/README.rst#prerequisites

#### for install skbuild
   python -m pip install --upgrade pip
   pip install cmake
   pip install pep517

 - install and build
   pip install git+git://github.com/couchbase/couchbase-python-client

 - 오류가 날 경우 /tmp 아래 생성된 디렉토리에서 build / install 을 실행. (에러 메시지가 자세함.)

### source clone 을 통한 build 방법.
 - python-client-sdk 2.5 로 진행.
 - git clone http://github.com/couchbase/couchbase-python-client
 cd couchbase-python-client 
 git checkout  -b release25 remotes/origin/release25
 python setup.py build_ext --inplace
 export PYCBC_BUILD=DISTUTILS
 pip install .

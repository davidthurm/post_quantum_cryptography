###
```
yum install cmake3
yum install ninja-build
wget https://github.com/ninja-build/ninja/releases/download/v1.11.1/ninja-linux.zip
unzip ninja-linux.zip
cp ninja /usr/bin
cmake3 -GNinja -DCMAKE_INSTALL_PREFIX=/opt/openssl/oqs .. -DOPENSSL_ROOT_DIR=/opt/openssl
/usr/bin/ninja
/usr/bin/ninja install
```
```
cd /opt/openssl
./Configure no-shared linux-x86_64 -lm
```

#########
```
git clone https://github.com/open-quantum-safe/openssh.git
```
```
vi ./oqs-scripts/build_liboqs.sh
# Change line 17 to cmake3
```
```
./oqs-scripts/clone_liboqs.sh
./oqs-scripts/build_liboqs.sh
```
```
./oqs-scripts/build_openssh.sh
```
```
oqs-test/run_tests.sh
```

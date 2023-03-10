# Install OpenSSL with PQC support

[Quantum Safe OpenSSL](https://github.com/open-quantum-safe/openssl#key-exchange)

```
yum install cmake3
```
[Ninja Install](https://github.com/ninja-build/ninja/releases)
```
yum install ninja-build
wget https://github.com/ninja-build/ninja/releases/download/v1.11.1/ninja-linux.zip
unzip ninja-linux.zip
cp ninja /usr/bin

```
cmake3 -GNinja -DCMAKE_INSTALL_PREFIX=/opt/openssl/oqs .. -DOPENSSL_ROOT_DIR=/opt/openssl
/usr/bin/ninja
/usr/bin/ninja install
```
```
cd /opt/openssl
./Configure no-shared linux-x86_64 -lm
```

# Install OpenSSH and compile in Support for PQC
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
[Quantum Safe OpenSSH](https://github.com/open-quantum-safe/openssh#building-oqs-openssh)
```
./oqs-scripts/build_openssh.sh
```
## If you wanted to test your install (take forever)
```
oqs-test/run_tests.sh
```
# Location of your test keys
/opt/openssh/oqs-test/tmp

# Location of your binaries
/opt/openssh/oqs-test/tmp/sbin

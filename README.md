# Building

``` sh
sudo dnf install rpmdevtools rpm-build
sudo dnf install 'dnf-command(builddep)'
sudo dnf builddep zed.spec
mkdir -p rpmbuild
ln -s $(pwd) $(pwd)/rpmbuild/SOURCES
spectool zed.spec -g -R --define "_topdir $(pwd)/rpmbuild"
env RPM_BUILD_NCPUS=4 rpmbuild zed.spec -ba --define "_topdir $(pwd)/rpmbuild"
```

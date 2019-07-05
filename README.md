H4K3ROM [LineageOS Source]
===========


```
mkdir H4K3RLite && cd H4K3RLite

repo init -u git://github.com/H4K3RLite/android.git -b lineage-16.0


/// Configure jack \\\
Jack is the currently used Java toolchain for building LineageOS 14.1 and 15.1. It is known to run out of memory often if not configured correctly - a simple fix is to run this command:

$ export ANDROID_JACK_VM_ARGS="-Dfile.encoding=UTF-8 -XX:+TieredCompilation -Xmx4G"
Adding that command to your ~/.bashrc file will automatically configure Jack to allocate a sufficient amount of memory (in this case, 4GB).

OPTIONAL: 
Turn on cache to speed up build
$ export USE_CCACHE=1
add that line to your ~/.bashrc file. Then, specify the max amount of disk space you want ccache:  
$ ccache -M 50G

then do:
repo sync --force-sync && . build/envsetup.sh && . vendor/lineage/h4k3rom.sh && LLVM_ENABLE_THREADS=2 && brunch oneplus3


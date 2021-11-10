# freebsdinfo
# mount FreeBSD img
partx -l FreeBSD-13.0-RELEASE-amd64-memstick.img
# 1:         1-    66584 (    66584 sectors,     34 MB)
# 2:     66585-  2130664 (  2064080 sectors,   1056 MB)
# 5:     66601-  2130664 (  2064064 sectors,   1056 MB)  <-- BSD partition

mount -t ufs -o loop,offset=$((66601*512)),ro,ufstype=ufs2 FreeBSD-13.0-RELEASE-amd64-memstick.img /mnt

```
  * dd if=/dev/sd* of=/mnt/* bs=4M status=progress oflag=sync conv=noerror,sync
  * To DD disk image to a zip file: dd if=/dev/sd* conv=sync,noerror bs=4M status=progress | gzip -c > /path/to/filename.gz
```
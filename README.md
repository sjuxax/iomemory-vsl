This is a version of iomemory-vsl that compiles on Linux 4.2 and GCC 5.2. Because the blob was not built with the same version of GCC, it may not be safe to use.

Unpatched build output:
```
/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kmem.c: In function ‘kfio_vmalloc’:
/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kmem.c:645:12: error: implicit declaration of function ‘vmalloc’ [-Werror=implicit-function-declaration]
     return vmalloc(size);
            ^
/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kmem.c:645:12: warning: return makes pointer from integer without a cast [-Wint-conversion]
/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kmem.c: In function ‘kfio_vfree’:
/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kmem.c:661:5: error: implicit declaration of function ‘vfree’ [-Werror=implicit-function-declaration]
     vfree(ptr);
     ^
/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kfio.c: In function ‘kfio_bind_kthread_to_node’:
/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kfio.c:1074:24: error: implicit declaration of function ‘cpus_weight’ [-Werror=implicit-function-declaration]
         if (cpumask && cpus_weight(*cpumask))
                        ^
make[3]: *** No rule to make target '/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kfio/x86_64_cc52_libkfio.o', needed by '/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/iomemory-vsl.o'.  Stop.
make[3]: *** Waiting for unfinished jobs....
  CC [M]  /home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kcsr.o
In file included from /home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kblock.c:59:0:
/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kblock.c: In function ‘kfio_dump_bio’:
/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kblock.c:937:53: error: ‘const struct bio’ has no member named ‘bi_cnt’
              msg, bio->bi_max_vecs, atomic_read(&bio->bi_cnt), bio->bi_io_vec,
                                                     ^
/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/include/fio/port/dbgset.h:202:58: note: in definition of macro ‘infprint’
 #define infprint(...)  kfio_print(KERN_INFO "fioinf " AT __VA_ARGS__)
                                                          ^
scripts/Makefile.build:258: recipe for target '/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kblock.o' failed
make[3]: *** [/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kblock.o] Error 1
cc1: some warnings being treated as errors
scripts/Makefile.build:258: recipe for target '/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kmem.o' failed
make[3]: *** [/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kmem.o] Error 1
cc1: some warnings being treated as errors
scripts/Makefile.build:258: recipe for target '/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kfio.o' failed
make[3]: *** [/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source/kfio.o] Error 1
Makefile:1398: recipe for target '_module_/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source' failed
make[2]: *** [_module_/home/youruser/fio/fusionio-files/ioDrive2/Linux_ubuntu-14.04/3.2.11/sw-source/x/iomemory-vsl-3.2.11.1581/driver_source] Error 2
make[2]: Leaving directory '/usr/src/linux-headers-4.2.0-18-generic'
Makefile:82: recipe for target 'modules' failed
make[1]: *** [modules] Error 2
```

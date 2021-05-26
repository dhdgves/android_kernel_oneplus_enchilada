# android_kernel_oneplus_enchilada

这是一个dotOS11的内核，为一加六准备。

事实上，这个文件夹应该被放在kernel/oneplus/sdm845,而不是kernel/oneplus/enchilada,具体根据sdm845-commom中的配置决定。

### 我做了什么

第一，单纯的升级了一下linux修订版本，尽量保持与[kernel.org](https://www.kernel.org/)中LTS的版本一致。

第二，因为要玩chroot的archlinux，开启了SVSY SPI的支持，修改了kronic_defconfig，这是sdm845-common中指定的默认配置（fakeroot需要，yay需要fakeroot）。如果你要玩ubuntu,可以选择在Makefile中把修订版本改为一个小于255的数字。

第三，升级过程中稍微解决了一个报错：fs/ext4/namei.c中，将确认文件系统是否加密的函数改成了IS_ENCRYPTED()，就目前来说是能编译通过了，否则会因为找不到修改前那个函数的定义而报错。


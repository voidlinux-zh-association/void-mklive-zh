## Void Linux 安装镜像与 rootfs 生成器

此仓库包含了 Void Linux 的其他程序
 * installer (The Void Linux el-cheapo installer for x86)
 * mklive    (The Void Linux live image maker for x86)

 * mkimage   (The Void Linux image maker for ARM platforms)
 * mkplatformfs (The Void Linux filesystem tool to produce a rootfs for a particular platform)
 * mkrootfs  (The Void Linux rootfs maker for ARM platforms)
 * mknet (Script to generate netboot tarballs for Void)

#### 编译的依赖关系
 * make

#### 依赖
 * Compression type for the initramfs image
   * liblz4 (for lz4, xz) (default)
 * xbps>=0.45
 * qemu-user-static binaries (for mkrootfs)

#### 使用方法

开始编译

    $ make
 
然后输出实用方法:

    $ ./mklive.sh -h
    $ ./mkrootfs.sh -h
    $ ./mkimage.sh -h

#### 例子

使用镜像源网站来构建镜像

    # ./mklive.sh -r https://mirrors.bfsu.edu.cn/voidlinux/current 
    
将构建的镜像设置为法式键盘

    # ./mklive.sh -k fr

使用构建 i686（在 x86\_64 上）的镜像并添加一些软件包：

    # ./mklive.sh -a i686 -p 'vim rtorrent'

使用存储在本地存储库中的包构建 x86\_64 musl 镜像：

    # ./mklive.sh -a x86_64-musl -r /path/to/host/binpkgs

有关详细信息，请参阅使用情况输出 :-)

# AppImage 构建集合

个人构建的各种开发工具类 AppImage 集合。

> AppImage 是一种 Linux 便携式应用程序格式，具有以下优势： 
> - 无需安装，单文件包含所有依赖
> - 跨发行版兼容，一次构建到处运行
> - 不污染系统环境，完全独立运行
> - 支持增量更新，便于分发维护
>
> 官方网站：https://appimage.org/
>
> 构建 AppImage 需要两个核心工具：
>
> - **appimagetool**：是最基础的 AppImage 打包工具，主要负责将 AppDir 转换为 AppImage。项目地址：https://github.com/AppImage/AppImageKit
>
> - **linuxdeploy**：是一个更高级的部署工具，不仅包含打包功能，还能自动处理依赖关系。项目地址：https://github.com/linuxdeploy/linuxdeploy
>

## 一、AppImage 构建详情

### 1. Bear

> Bear 是一个用于生成编译命令数据库（compile_commands.json）的强大工具。它主要用于：
> - 为 LSP（Language Server Protocol）服务器如 clangd、ccls 提供项目的编译信息
> - 帮助代码补全、跳转定义、语法检查等 IDE 功能正常工作
> - 支持拦截几乎所有类型的构建命令，包括 make、cmake、ninja 等
> - 特别适合在大型 C/C++ 项目中使用，可以准确追踪所有编译单元的编译标志

#### 1.1. Ubuntu 18.04.6 LTS

##### 1.1.1. 构建参数

```bash
xxx
```

##### 1.1.2. 源码版本信息
- linuxdeploy 版本：
  - x.x.x 
- appimagetool 版本：
  - x.x.x

### 2. Git

#### 2.1. Ubuntu 18.04.6 LTS

##### 2.1.1. 构建参数

```bash
./configure \
    --prefix=/usr \
    --with-gitconfig=/etc/gitconfig \
    --with-python=/usr/bin/python3 \
    --with-openssl \
    --with-curl \
    --with-expat \
    --with-tcltk \
    --with-libpcre2 \
    --with-zlib \
    --with-editor=/usr/bin/editor \
    --enable-pthreads \
    --enable-maintainer-mode \
    --enable-git-daemon \
    --enable-http \
    --enable-https \
    --enable-ipv6 \
    --enable-werror=no \
    --enable-largefile
```

##### 2.1.2. 源码版本信息

- linuxdeploy 版本：
  - 2.48.1
- appimagetool 版本
  - 2.48.1

## 二、使用说明

### 1. 运行方法
```bash
# 添加执行权限
chmod +x *.AppImage

# 直接运行
./<appimage-name>.AppImage
```

### 2. 兼容性
- 所有 AppImage 都在构建平台上进行过功能测试（不保证 100% 覆盖）

- 如遇运行问题，请先确认是否已安装 FUSE。如果系统没有 FUSE，可以使用解压模式运行：

  ```bash
  ./*.AppImage --appimage-extract
  ./squashfs-root/usr/bin/xxx
  ```

  

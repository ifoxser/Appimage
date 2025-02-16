# Git AppImage

## 1. 运行方法
```bash
# 添加执行权限
chmod +x *.AppImage

# 直接运行
./<appimage-name>.AppImage
```

## 2. 兼容性
- 所有 AppImage 都在构建平台上进行过功能测试（不保证 100% 覆盖）

- 如果遇到运行问题，请先确认是否已安装 FUSE。如果系统没有 FUSE，可以使用解压模式运行：

  ```bash
  ./*.AppImage --appimage-extract
  ./squashfs-root/usr/bin/xxx
  ```

  

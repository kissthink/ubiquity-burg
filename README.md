ubiquity-burg
=============

ubiquity-2.18.8 for ubuntukylin 1404(trusty)

(1)用burg替换部分相关打grub关键字：
./d-i/source/grub-installer/grub-installer
	:1,$s/grub-pc/burg-pc/g
	:1,$s/grub-install/burg-install/g
	:1,$s/update-grub/update-burg/g
(2)./scripts/install.py
(3)./scripts/plugininstall.py
(4)./ubiquity/misc.py
(5)./data/ubiquity.desktop.in
(6)覆盖安装修改
./d-i/source/partman-auto/automatically_partition/replace/choices         
./d-i/source/partman-auto/automatically_partition/replace/do_option
(7)重新安装安装修改：
./d-i/source/partman-auto/automatically_partition/reuse/choices
./d-i/source/partman-auto/automatically_partition/reuse/do_optition
(8)livcd中双击桌面上的安装系统图标时使用preseed文件（--automatic）
./data/ubiquity.desktop.in
(9)python代码修改：
./ubiquity/plugins/ubi-partman.py
(10)去掉没有swap分区的警告：
./d-i/source/partman-basicfilesystems/check.d/check_swap
(11)安装类型选择界面中文化文字修改：
vim ./debian/real-po/zh_CN.po 
(高级安装；
注意：这会删除原有系统的所有文件，可能会用完硬盘的所有剩余空间。； 
利用空闲分区安装正式版2.0；
利用硬盘上现有的空闲分区安装系统，不会影响硬盘上已经安装的其他操作系统；
覆盖原有系统)
(12)语言列表修改，由于i18n.py是从/usr/share/localechooser/languagelist.data.gz读取打列表，所以需要修改./d-i/source/localechooser/languagelist(从/d-i/source/localechooser/debian/rules可以分析到)

vim快捷键：
V：可视;
y：复制;
dd：删除;
p：粘贴.

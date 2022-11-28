---
layout: post
title: 准备工作
author: Johnnywow
tags:
- VASP
date: 2022-11-28 15:44 +0800
---
# 安装前准备

1. 了解如何使用Linux & 上传文件到HPC。  
  - Linux 命令，[file]代表的是一个文件，[target]代表的是一个路径。  
  `pwd` - 显示当前路径  
  `ls` - 列出当前路径下的文件及文件夹  
  `cd [target]` - 进入`[target]`文件夹  
  `mv [file] [target]` - 移动`[file]`到`[target]`位置  
  `cp [file] [target]` - 复制`[file]`到`[target]`位置  
  `tar -xf [file].tar.gz` - 解压`[file].tar.gz`文件，Linux的压缩包一般为这个格式。  
  `source [file]` - 加载`[file]`环境  
  `make [file]` - 编译/安装`[file]`软件  
  `vi [file]` - 用vi文本编辑器编辑`[file]`，由于vi的使用比较复杂，需要一定学习时间，刚开始只需要了解如何编辑和保存即可。即如何进入和退出INSERT模式，如何:wq保存，如何:q!强制退出即可。详细教程请移步[这里](https://www.runoob.com/linux/linux-vim.html)  
  - 上传文件到HPC  
  Windows用户推荐使用Xftp，Mac用户暂时无能为力（逃。  
  HPC 应该会有对应网页端，可以用来上传和下载软件，管理作业等。具体情况请咨询您的HPC提供商。 
  
2. 准备赝势文件  
  - 这个百度一下吧   
  - 上传后用 `tar -xf pesudo.tar.gz` 解压到当前目录

3. 安装vaspkit  
  - vaspkit的下载地址在[这里](https://vaspkit.com/)  
  - 上传后用 `tar -xf vaspkit.x.x.x.tar.gz` 解压到当前目录   
  - `ls` 一下  
  - `cd [vaspkit.x.x.x]` 进入vaspkit目录  
  - `ls` 一下  
  - `bash setup.sh` 按照提示修改~/.vaspkit文件内容  
  - `vi ~/.vaspkit`，然后按`i`键左下角会显示`-- INSERT --`，表示当前在输入模式。  
  - 修改 `LDA_PATH` 和 `PBE_PATH`，将2中的赝势文件路径添加到 `=` 号后面，如  
  ```
  PBE_PATH =  ~/softwares/pseudopotentials/potpaw_PBE  
  ```  
  - 添加python路径，`PYTHON_BIN = /usr/bin/python`，不知道python路径在哪的可以输入`which python`  
  - 按`esc`健，连续输入`:wq`，回车保存。  
  - `source ~/.bashrc`一下  
  - 这时候输入`vaspkit`会出现  
  ```
            \\\///
           / _  _ \         Hey, you must know what you are doing.
         (| (o)(o) |)       Otherwise you might get wrong results.
 o-----.OOOo--()--oOOO.------------------------------------------o
 |         VASPKIT Standard Edition 1.4.0 (02 Nov. 2022)         |
 |         Core Developer: Vei WANG (wangvei@icloud.com)         |
 |      Main Contributors: Gang TANG, Nan XU & Jin-Cheng LIU     |
 |  Online Tutorials Available on Website: https://vaspkit.com   |
 o-----.oooO-----------------------------------------------------o
        (   )   Oooo.                          VASPKIT Made Simple
         \ (    (   )
          \_)    ) /
                (_/
 ===================== Structural Utilities ======================
 1)  VASP Input-Files Generator    2)  Mechanical Properties
 3)  K-Path for Band-Structure     4)  Structure Editor
 5)  Catalysis-ElectroChem Kit     6)  Symmetry Analysis
 7)  Materials Databases           8)  Advanced Structure Models
 ===================== Electronic Utilities ======================
 11) Density-of-States             21) Band-Structure
 23) 3D Band-Structure             25) Hybrid-DFT Band-Structure
 26) Fermi-Surface                 28) Band-Structure Unfolding
 31) Charge-Density Analysis       42) Potential Analysis
 51) Wave-Function Analysis        62) Magnetic Properties
 65) Spin-Texture                  68) Transport Properties
 ======================== Misc Utilities =========================
 71) Optical Properties            72) Molecular-Dynamics Kit
 74) User Interface                78) VASP2other Interface
 91) Semiconductor Kit             92) 2D-Material Kit
 0)  Quit
  ```
  就说明成功了！

   最后，善用**Google**

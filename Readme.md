Rokid 投屏工具部署
---------------------------

#### 下载
*    地址：https://github.com/xhlstar/rokid_scrcpy
     *  M 芯片
     如果是M1 M2...芯片，要选择MChip分支后再进行下一步
     * Intel 芯片
     main 分支
*    点击code 然后 ZIP包压缩，解压到一个路径


#### Homebrew 
*   使用中科大的源进行下载[简书连接](https://www.jianshu.com/p/358e8ffd7d08)
    /bin/zsh -c "$(curl -fsSL https://gitee.com/cunkai/HomebrewCN/raw/master/Homebrew.sh)"

*   环境变量设置
    *   M芯片
        *  fish .config/fish/config.fish增加
         set -x PATH /opt/homebrew/bin $PATH
        *  bash .bashrc
      export PATH=/opt/homebrew/bin;$PATH
      *   Intel 芯片自动能找到brew

*   在终端内测试
    brew update

#### ADB
*   brew install android-platform-tools

*   环境变量设置
    *   M 芯片
          *  fish .config/fish/config.fish增加
          set -x PATH /Users/xuhailiang/Library/Android/sdk/platform-tools $PATH
          *  bash 
          export PATH=/Users/xuhailiang/Library/Android/sdk/platform-tools;$PATH
#### 安装scrcpy环境

*     brew install ffmpeg

#### 部署环境
*    cd rokid_scrcpy

*    M 芯片
        *    cp /opt/homebrew/share/scrcpy/scrcpy-server ./scrcpy-server-old
        *    cp ./scrcpy_server /opt/homebrew/share/scrcpy/scrcpy-server

*   Intel 芯片
    *    cp /usr/local/share/scrcpy/scrcpy-server ./scrcpy-server-old
    *    cp ./scrcpy_server /usr/local/share/scrcpy/scrcpy-server
*   赋予可执行权限，并在MAC 安全设置中允许scrcpy
    *   chmod +x ./scrcpy

#### 执行
*   adb shell setprop debug.rokid.2dof 1
*   ./scrcpy -b 4M --video-codec=h265
*   插拔眼镜

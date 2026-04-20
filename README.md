# packages

## 这里的包分两个版本，也有插件改了位置适配老版主题
## 一个json新版的插件openwrt-23.05
## 一个lua老版的插件lede-18.06
### 你用什么源码就git啥，有个别插件做了修复，有插件是反向解的都能用不能用的话issues！
###  仓库主要是lede源码在做修改！！！
### 编辑 feeds.conf.default 文件，在末尾添加或者源码根目录下载：

### 记得删除这些
         feeds/packages/net/mosdns
         rm -rf feeds/packages/net/msd_lite
         rm -rf feeds/luci/applications/luci-app-mosdns
         rm -rf feeds/luci/applications/luci-app-msd_lite
         rm -rf feeds/luci/applications/luci-app-ttyd


       src-git Plugin https://github.com/Little-ku/Plugin.git
       #src-git Plugin https://github.com/Little-ku/Plugin.git;lede-23.05
       #src-git Plugin https://github.com/Little-ku/Plugin.git;lede-18.06
       
       
       ./scripts/feeds update -a
       ./scripts/feeds install -a -f
       
       make menuconfig
       make V=s -j$(nproc)
       


### 单独编译该包（用来提前测试用是不是你需要的）
### 记住你用啥源码就用哪个包比如老版本就第二个，新版就第一个!!!

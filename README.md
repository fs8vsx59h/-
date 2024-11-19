- 在某网站购买了视频发现不能下载，网上搜了一下发现有同样的受害者  
- 方法提供者: https://github.com/yt-dlp/yt-dlp/issues/2537  
- 这个叫 pzhlkj6612 的老哥提供了完整的解密视频并下载的思路，我只是整理  
- 用到的工具是 https://github.com/Last-Order/Minyami   
- 这个工具是一个独立完整的下载器，在境外某台安装了 nodejs 的 VPS上安装就可以，免得因网络问题导致下载失败   
- 首先进入想要下载视频的网站（某N开头网站）打开你要下载的视频


  

## 下面是完整步骤

1. 按F12打开chrome调试工具，选中“网络”
2. 在调试工具的搜索框里输入“mediaplaylist” ，然后会看到一个链接，点击“标头”，复制里面的网址，粘贴到地址栏，按回车会下载一个m3u8文件
3. 在调试工具搜索框里输入“key",同样有个链接，同样的方法下载key文件
4. 将key文件转换为16进制文本，linux平台:
```bash
cat key | xxd -ps
```
5. 安装Minyami，具体请参考Minyami中文文档
6. 使用Minyami下载视频，Minyami有自动拼接和解密功能，非常方便，希望下载成功的给Minyami作者点个⭐
```bash
minyami --download "m3u8文件路径" --key "转换为16进制字符串的key"
```

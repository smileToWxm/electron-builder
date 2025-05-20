1、修复 electron-updater 模块  getCacheUpdateFileName方法，在遇到无后缀url时，直接使用url作为文件名报错问题。
新增了 releaseName字段，若在laterst.yml加入 releaseName，则优先取其作为文件名。
例如 url为 https://xxx.xxx.com/xxx/d0le6oc2v2fgt7i7ejag 时，则在下载时就会从 getCacheUpdateFileName方法里获取文件名，就会变成 
temp-https://xxx.xxx.com/xxx/d0le6oc2v2fgt7i7ejag  这样的非法路径，导致下载失败

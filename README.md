# ceshi2
mac =new memcache();
if(!mac->connect('127.0.01','127099')){
  echo "链接memcache失败";
}
//需要MD5加密
//第一个参数键
//第二个参数值
//第三个参数 0 不压缩 MEMCACHE_COMPRESSED 压缩 
//第四个参数 缓存时间单位（秒） 小于30天直接用秒 大于30天使用时间搓 time()+60*60*24*100
mac->set('key','测试内容'，MEMCACHE_COMPRESSED，50);
mac->replace('key','测试内容'，MEMCACHE_COMPRESSED，50);
mac->get('key');
mac->delete('key');
mac->flush();
mac->close();

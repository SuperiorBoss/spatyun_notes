```
LoadingCache<String/*bind#time for hour*/, List<String>/*绑定/解绑cluster#ip#vip*/> failedInfos =
CacheBuilder.newBuilder().expireAfterWrite(62, TimeUnit.MINUTES).build(new CacheLoader<String, List<String>>() {
    @Override
    public List<String> load(String s) throws Exception {
    return new ArrayList<String>();
    }
});
```



**expireAfterWrite\(long, TimeUnit\)**：缓存项在给定时间内没有被写访问（**创建或覆盖**），则回收。如果认为缓存数据总是在固定时候后变得陈旧不可用，这种回收方式是可取的。

```
  /**
     * 通过集群环境版本获取VIP
     * @param clusterId  集群Id
     * @param environment  环境
     * @param version  版本
     * @return
     * @throws Exception
     */
      public  Vip getVipByClusterEnvVersion(long clusterId, int environment,String version) throws Exception {
        return  vipRepository.getVipByClusterVerEnv(clusterId, version,environment);
    }
```




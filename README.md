infinispan-memcached-store
=====================

A Memcached Cache Store to JBoss Infinispan released under the LGPL.

It's intended to allow cache overflowing to Memcached - to have a fast (in-memory) access without paying a performance
penalty due long garbage collector cycles.

Configuration
-------------

```java
   ConfigurationBuilder configBuilder = new ConfigurationBuilder();
   configBuilder.loaders().addStore(MemcachedStoreConfigurationBuilder.class)
    .hostname("localhost")
    .port(11211)
    .fetchPersistentState(false)
    .ignoreModifications(false)
    .purgeOnStartup(false)
    .async().enable();
   Configuration config = configBuilder.build();
   cacheManager = new DefaultCacheManager(config);

   Cache<K,V> cache = cacheManager.getCache();
```


This code is brought to you by <a href="http://www.c2b2.co.uk/oracle_coherence">C2B2 The Leading Independent middleware Experts</a>





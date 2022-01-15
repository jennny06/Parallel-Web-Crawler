##Steps
1. Update `ConfigurationLoader` and `CrawlerConfiguration`
   1. Update `Read` method using Jackson 
   2. Add Jackson @JsonDeserialize annotation that set builder pattern in CrawlerConfiguration
   3. @JsonProperty to map JSON property names and builder methods
   4. Update `Load` method to create reader from path
2. Update `CrawlResultWriter`
   1. Update `write` method with path
   2. Update `write` method with writer
3. Update `Main`
   1. Call `CrawlResultWriter` to write to file
4. Update `ParallelWebCrawler` based on SequentialWebCrawler
   1. Extend `RecursiveAction` to create an internal crawler for subtasks
   2. invoke all subtasks
5. Reimplement `WordCounts` in Stream
   1. use of collectors.toMap
6. 

##Class

1. json
   1. CrawlerConfiguration
      1. 一个内部类 Builder to create CrawlerConfiguration instance 
   2. CrawlResult 
      1. 一个内部类 Builder to create CrawlResult instance
2. Main
3. parser
4. profiler
5. WebCrawler Interface
   1. 使用 dependency injection module
   2. 可以实现 singleton
   3. SequentialWebCrawler
   4. ParallelWebCrawler
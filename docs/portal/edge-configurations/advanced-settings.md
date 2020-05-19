# Advanced Settings

| **Fields**              | **Description**                                      |
| ----------------------- | -----------------------------------------------------|
| Cache Key Hostname      | Enter the hostname to use in the cache key. By default, the incoming Host Header value is used. The cache key is the index to the content stored in the server cache.|
| Has Beian               | Specify whether all hostnames in this property have [Beian in China](</docs/edge-logic/faq.md#china-delivery-and-beian>). If **No** is selected, the CDN360 proxy servers located in mainland China will not serve this property in order to abide with the laws in China. All visitors will be served by servers outside China. If **Yes** is selected, the CDN360 API server confirms the Beian status of all hostnames. Once confirmed, visitors in mainland China will be served by the CDN360 servers in mainland China.|
| Load Balancer Hash Key | CDN360 PoPs use multiple tiers of load balancing to distribute client requests to different servers. By default, consistent hashing is used, with the URL used as the hash key. Users with additional load balancing requirements can use this field to add variables to the hash key to distribute requests more evenly. One example that can benefit from this feature is when all requests carry the same URL, but use a particular header to indicate the resources. By default, this field is empty. <br><br>Values entered in this field must meet the following requirements.<ul><li>Contain alphanumeric characters and an underscore, equals sign, dollar sign, and ampersand.</br><li>Variable names must be: `$http_name`, `$cookie_name`, or `$arg_name`.<li>At least one variable must be specified. No more than three are permitted.<li>The total length value cannot exceed 100 characters.<li>The following examples show valid values:<br>`$http_abc`<br>`abc=$http_abc&def=$http_def&`<br>`c_123=$cookie_123`<br>`abc=$http_abc=$http_def`<br>`$http_abc&$http_def`<br></ul>

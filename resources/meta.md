## Meta 汇总
### LeetCode
2024年1-4月份手动汇总贴子里的一些题目


| ------ | --------- |
| 162    | 8         |
| 88     | 4         |
| 215    | 4         |
| 314    | 5         |
| 938    | 4         |
| 138    | 3         |
| 227    | 3         |
| 71     | 2         |
| 146    | 2         |
| 1570   | 2         |
| 236    | 2         |
| 50     | 2         |
| 1091   | 2         |
| 973    | 2         |
| 560    | 2         |
| 1      | 1         |
| 14     | 1         |
| 15     | 1         |
| 21     | 1         |
| 23     | 1         |
| 49     | 1         |
| 56     | 1         |
| 65     | 1         |
| 1004   | 1         |
| 101    | 1         |
| 1071   | 1         |
| 1249   | 1         |
| 133    | 1         |
| 1443   | 1         |
| 1428   | 1         |
| 1650   | 1         |
| 1762   | 1         |
| 1539   | 1         |
| 160    | 1         |
| 210    | 1         |
| 219    | 1         |
| 267    | 1         |
| 269    | 1         |
| 301    | 1         |
| 310    | 1         |
| 332    | 1         |
| 334    | 1         |
| 347    | 1         |
| 348    | 1         |
| 398    | 1         |
| 408    | 1         |
| 426    | 1         |
| 428    | 1         |
| 435    | 1         |
| 528    | 1         |
| 543    | 1         |
| 680    | 1         |
| 691    | 1         |
| 827    | 1         |
| 958    | 1         |
| 983    | 1         |
| 986    | 1         |
| 116    | 1         |

### System Design
- Design a Ads Click Aggregation System (Frequency: +++)
  - 要点在于real time processing huge amount of data
  - 参考资料
    - Alex Xu (BytebyteGo)
    - Hello Interview
- Design a streaming service (Frequency: +++)  
  - 某个帖子提到的，需要支持 video play、recommendation、subscription。视频观看网站，类似 youtube/netflix, and similar one as spotify。Functional requirement：1. 能够切换清晰度观看。2. 记录用户视频观看到哪里了，用户下次点开视频时自动从上次的位置继续。High level design 讲了没多久就开始被打断 deep dive，因为是 infra 岗，问的问题基本都围绕 non-functional requirements。
  - 参考资料
    - Alex Xu (BytebyteGo)
    - Scott Shi
    - Huahua
    - Grokking
- 设计 live comments (Frequency: ++)
  - 参考资料
    - Hello Interview
    - interviewing.io
- 设计 leetcode (Frequency: ++)
  - 建议稍微要提到security方面的concern，然后基本思路应该就是用isolated env (container)去分布式地跑code。
  - 参考资料
    - Hello Interview
    - Scott Shi
- 设计一个 gaming leaderboard，需要返回当前整个游戏的 top N player、当前用户的前后 N 个 player，返回当前用户朋友的 top N player、当前用户朋友的前后 N 个 player (Frequency: ++)
  - 参考资料
    - Alex Xu (BytebyteGo)
    - SDFC
    - Hello Interview 有Top K Youtube Video可以用来比较，两者的区别在于game leaderboard由于size比较小，可以就存在一个Redis server，但是Youtube需要一个aggregation。但是如果game leaderboard的size成为一个issue以后，就可以用类似top k video的解法
- chess 带 leaderboard， 主要问了 game service 里可以撤回上一步要怎么设计， leaderboard 怎么设计 ++, 设计一个脸书上的在线棋牌游戏，不需要考虑匹配机制，两人游戏, [Algebraic notation (chess)](https://en.wikipedia.org/wiki/Algebraic_notation_(chess)) (record moves) (Frequency: ++)
  - https://github.com/tssovi/grokking-the-object-oriented-design-interview/blob/master/object-oriented-design-case-studies/design-chess.md
- Design ticket master / stubhub (Frequency: ++)
  - 类似的这种处理用户可能大量预订到一样的entity的题目，也包括flight、hotel booking reservations
  - 参考资料
    - Hello Interview
    - Alex Xu (BytebyteGo) - Hotel Reservation Systems
- Design Instagram
  - 其实感觉跟news feed是类似的题目
- Proximity
  - 参考资料
    - Alex Xu (BytebyteGo)
- Design Yelp / Google Map
  - 类似的还有Nearby Friends， Uber
  - 参考资料
    - Alex Xu (BytebyteGo) - Google Map
    - Scott Shi
    - Hello Interview - Uber
    - Hua hua - Yelp
- Design Metrics monitoring
  - 感觉可以类比ads click
  - 参考资料
    - Alex Xu (BytebyteGo)
- Design web crawler
  - 贴子里提到的，有一些限定条件，比如说一万台机器，尽可能让每台机器的 load evenly distributed。这道题做了非常多的 back of envelope calculation，要计算 different instance types handling different types of work，应该是比较贴近 production 的一道题。但这个题目还有个限制条件，降低带宽使用，毛子指着我设计一个部分问有没啥问题，我说了 bottleneck，他点点头，然后就接着 design 了 (Frequency: +)
  - 参考资料
    - Alex Xu (BytebyteGo)
    - Hello Interview
    - Scott Shi
    - Hua hua
- Presence indicator
  - 贴子里提到的，status 查询，重点是考察怎么建索引要搜索更高效。
  - 参考资料
    - Alex Xu (BytebyteGo) - 在chat system那章有提到status indicator的implementation
    - SDFC
- Design a hotel booking system。
  - 贴子里提到的，hotel 得 confirm 预定，得 pull availability 等等
  - 参考资料
    - Alex Xu (BytebyteGo)
- Design an auction system
  - 贴子里提到的，用户可以 view current bid price 然就可以 bid with higher price。 主要问了如果 bid at same price 怎么解决 conflict。以及怎么 scale 一个很 hot 的 auction。
  - 参考资料
    - SDFC
- Design chat system
  - 参考资料
    - Alex Xu (BytebyteGo)
    - Hello Interview - Whatsapp
    - Scott Shi - Design Slack
- Design News feed
  - 参考资料
    - Alex Xu (BytebyteGo)
    - Hello Interview
    - Scott Shi
- Design Google Drive
  - 贴子里提到的，是个 infra 大神的感觉，问了些怎么处理 upload 时 failure 的情况，我说了设计一个 daemon job 去检查新增的 file 以及用 sqlite 来存类似 WAL 的东西。不要求 high QPS 但要求 high reliability / durability，我用了 S3 似乎有点作弊，他可能想要听我说怎么 replicate uploaded files
  - 参考资料
    - Alex Xu (BytebyteGo)
    - Hello Interview - dropbox
    - Huahua - Dropbox
- 设计 search for FB post。主要讨论了 inverted index，post privacy?
  - 参考资料
    - https://engineering.fb.com/2013/10/24/core-infra/under-the-hood-building-posts-search/
- Design top k songs in Spotify
  - 参考资料
    - SDFC
- Design camel camel camel / price tracker
  - 感觉可以参考一些web crawler和notification system的思路
  - 参考资料
    - SDFC

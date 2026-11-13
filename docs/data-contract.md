# 业务资料约定

die_id由dies.id给出；day为项目日历整数日。tests的event_day表示发生时间，received_day表示资料可见时间，sequence为芯片内测试顺序。reference.share是冻结产品份额。

每行id在该表内唯一，文件顺序不代表业务事件顺序。清单schema=1，各表登记文件名、字节长度、SHA256、行数及完整字段集合，未知版本或内容变化应重新登记。金额及测量数值均为独立资料，不代表任何现实机构的经营数据。

- dies：id、wafer、product、first_day。
- tests：id、die、sequence、event_day、received_day、passed、revoked。
- reference：id、share。

normal与boundary是相互独立的资料包，不能直接拼接重复id。引用字段按本项目domain.py的REFERENCES登记。读取检查只检查完整性、身份及这些直接引用，不替代领域分析中的可识别性、时点可见性或可行性判断。

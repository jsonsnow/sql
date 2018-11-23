#### sql n + 1问题
N+1 查询问题原因

* 1.执行了一个单独的sql语句来获取结果列表(就是+1)
* 2.对返回的每条记录，执行了一个查询语句来为加载细节

解决方法一，把查询打包
```
select * from xxx_1 let outer join xxx_2 on xxx_1.id=xxx_2.id
```

对于不需要xxx_2的还可以不用去查询xxx_2
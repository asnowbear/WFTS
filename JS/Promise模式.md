
# Promise

## primise 规范

- 三种状态：等待(pending)、已完成(fulfiled|Resolved)、已拒绝(rejected)

- 必须从是 pending -> fulfiled || pending -> rejected

- 必须实现 then 方法，then必须返回一个 promise,同一个promise的then可以多次调用

- 

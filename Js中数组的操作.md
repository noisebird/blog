### JavaScript中数组的操作
> 数组是JavaScript中的一种引用数据类型，一种用于存储复杂数据的数据结构。

 
| 方法名 | 参数 | 返回值 | 描述 | 
| :----  |:-----:| :--:| 
|filter   | - |  过滤后的数组    |  过滤出回调函数中返回为true的条目组成的数组 |
|map      |(callback) | 返回一个新数组由map返回值组成 | 会遍历数组所有的项，回调函数接受三个参数,分别为value，index，self|
|every    |(callback) | bool值   | 回调函数返回布尔值，全部为true，由every返回true|
|some     |(callback) | bool值   | 回调函数返回布尔值，有一个返回为true，则返回true|
|sort     | |   | 排序（字符规则），返回结果|
|join     |（string） | string  | 使用分隔符，将数组转为字符串并返回|
|reduce   | |    | 创建一个有回调函数中返回值组成的数组|
|splice   |(start, deleteCount, ...values) |  返回删除的数据(数组)   | 删除指定位置，并替换 |
|slice    |（start, end） |  截取出来的数组  | 截取指定位置的数组，并返回|
|reverse  | - |    返回反转后的数据    | 反转数组 |
|includes  | |      | 创建一个有回调函数中返回值组成的数组|
|find    |(callback) | 返回找到的那一条数据    | 查找数组中的数据|
|findIndex  |(callbakc) | 返回找到数据的索引      | 查找数组中是否包含指定条件的数据，有返回索引，无返回-1 |
|concat   |（array） | 返回拼接后的数组     | 拼接数组|
|forEach   |回调函数 |  -   |遍历数组所有的项，回调函数接受三个参数,分别为value，index，self|
|flat     | |  | 创建一个有回调函数中返回值组成的数组|
|flatMap  | |      | 创建一个有回调函数中返回值组成的数组|
|push     |(any) | 返回增加的数据  | 创建一个有回调函数中返回值组成的数组|
|pop    | - |  返回删除的数据  | 删除最后一位，并返回删除的数据|
|shift   |(any) |  返回数组的长度   | 在最后一位新增一或多个数据，返回长度|
|unshift  |- |  返回出栈的数据    | 创建一个有回调函数中返回值组成的数组|

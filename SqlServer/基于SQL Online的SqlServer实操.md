## 1. SQL Online

`SQL Online`提供免费的在线数据库环境，截止[2023-3-21]()日，它支持的数据库类型有`MariaDB、PostgreSQL、SQLite、SQLServer`。其它类似的产品还有`SQL Fiddle、DB Fiddle、db<>fiddle`等

> - SQL Online: https://sqliteonline.com/
> - SQL Fiddle: http://sqlfiddle.com/
> - DB Fiddle: https://www.db-fiddle.com/
> - db<>fiddle: https://dbfiddle.uk/

## 2. Connect SQL Server

![image-20230321135811164](%E5%9F%BA%E4%BA%8ESQL Online%E7%9A%84SqlServer%E5%AE%9E%E6%93%8D.assets/image-20230321135811164.png)

来到首页后，可以选择连接`MS SQL`（即Microsoft SQL Server），目前提供的是2019版本，点击ok即可！

![image-20230321135741460](%E5%9F%BA%E4%BA%8ESQL Online%E7%9A%84SqlServer%E5%AE%9E%E6%93%8D.assets/image-20230321135741460.png)

## 3. 页面划分

连接成功后，我们可以将整个页面划分为五个部分：

![image-20230321140341576](%E5%9F%BA%E4%BA%8ESQL Online%E7%9A%84SqlServer%E5%AE%9E%E6%93%8D.assets/image-20230321140341576.png)

- 一号区域显示当前你创建的一些表，默认有一张demo表
- 二号区域是编写SQL命令的地方
- 三号区域是一些指令，包括运行、导入与导出等
- 四号区域显示的是你的SQL运行结果
- 五号区域显示的是你在一个会话期间操作的历史记录

> 这里我们通过使用`sp_columns demo;`命令查看了`demo`表的所有字段信息

## 4. 关闭自动补全

网站默认开启自动补全：

![image-20230321141019572](%E5%9F%BA%E4%BA%8ESQL Online%E7%9A%84SqlServer%E5%AE%9E%E6%93%8D.assets/image-20230321141019572.png)

如果你想要关闭它，点击右上角的设置小齿轮，勾选上`Disable autocomplite`即可：

![image-20230321141217656](%E5%9F%BA%E4%BA%8ESQL Online%E7%9A%84SqlServer%E5%AE%9E%E6%93%8D.assets/image-20230321141217656.png)

## 5. Simple Code

```mssql
DROP TABLE if EXISTS qingke;

CREATE TABLE qingke (
    id INT PRIMARY KEY IDENTITY (1, 1),
    name VARCHAR (50) NOT NULL,
  	gender INT NOT NULL,
    phone VARCHAR(11)
);

insert INTO qingke (name, gender) VALUES ('PengBin', 1);
insert into qingke values ('QingKe', 0, '12345678910');

SELECT * FROM qingke;

ALTER TABLE qingke ADD CONSTRAINT gender CHECK (gender = 0 OR gender = 1)

ALTER TABLE qingke ADD CONSTRAINT phone CHECK(len(phone) = 11 AND phone LIKE '[0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9][0-9]');

INSERT INTO qingke VALUES ('qingke', 1, '01987654321');

SELECT * FROM qingke;

INSERT INTO qingke VALUES ('qingke', 1, '0198764a221');

SELECT * FROM qingke;
```

## 参考

- [SQL Server常见的约束条件](https://blog.csdn.net/Mr_YanMingXin/article/details/105003495)
- [SQL Server教程](https://www.yiibai.com/sqlserver)
- [使用SqlServer图形化工具创建数据库](https://blog.csdn.net/CesareBorgia/article/details/110190797)
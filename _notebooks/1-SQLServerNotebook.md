---
jupyter:
  jupytext:
    formats: ipynb,md
    text_representation:
      extension: .md
      format_name: markdown
      format_version: '1.3'
      jupytext_version: 1.13.8
  kernelspec:
    display_name: Python 3 (ipykernel)
    language: python
    name: python3
---

# SQL Server Azure Data Studio Notebook
> A tutorial of SQL Server.

- toc: true 
- badges: true
- comments: true
- categories: [R]


```sql azdata_cell_guid="cf4b28e8-2941-4bc7-862e-121670381d2c"
USE AdventureWorks2014;
```

```sql azdata_cell_guid="0cd776af-37e5-4266-acdb-53352e05d555" tags=[]
--https://docs.microsoft.com/en-us/sql/azure-data-studio/notebooks/notebooks-sql-kernel
SELECT distinct Title FROM Person.Person
SELECT distinct Type, Category FROM Sales.SpecialOffer
```

```sql azdata_cell_guid="8e0b39b5-3783-43aa-a0ab-fc1823832721"
SELECT distinct size, color from Production.Product
```

<!-- #region azdata_cell_guid="26d8ebaa-1696-4fc9-b853-dab4a8876a00" language="" -->
# Edvancers SQL Server Course
<!-- #endregion -->

<!-- #region azdata_cell_guid="584d1c22-6e93-4465-bd8c-d3cd48eea892" -->
# Data Types
<!-- #endregion -->

<!-- #region azdata_cell_guid="a6636571-9e60-4803-8640-1ff6859de057" -->
![Imgur](https://i.imgur.com/Q2k1r4W.jpg)
<!-- #endregion -->

<!-- #region azdata_cell_guid="5f22d36f-2697-48f2-b17a-4e40d39e67f2" language="sql" -->
# Date Datatype
<!-- #endregion -->

```sql azdata_cell_guid="10a33a62-8f80-4fa8-9e49-b5d91169448f"
Declare @myDate date = '02-02-2016'
Select @myDate as MyDate
```

```sql azdata_cell_guid="a858c15a-d07a-45c1-a6ce-db94bca7291a" tags=[]
Declare @myDateTime datetime = '02-02-2016'
Select @myDateTime as MyDateTime
```

```sql azdata_cell_guid="9519d7c0-b851-41c6-822e-9204e72b4fc6"
Declare @myTime time = '16:25:42.1214'
Select @myTime as MyTime
```

```sql azdata_cell_guid="c3eb7e0d-f841-4517-ae43-3c2b70214f96"
Declare @myTime time(2) = '16:25:42.1214'
Select @myTime as MyTime
```

<!-- #region azdata_cell_guid="647ab2dd-a2e8-44c0-a1d1-4eba7efa0562" language="sql" -->
<table>
<tr>
    <td>
        <a href="https://imgur.com/h0zk8Zn"><img src="https://i.imgur.com/h0zk8Zn.jpg" title="source: imgur.com"  Height = "250" width="350"/></a>
    </td>
</tr>
</table>
<!-- #endregion -->

<!-- #region azdata_cell_guid="12185dfa-73e9-43c3-9b9c-b2666ed17eb8" language="" -->
# Charecter Datatype
<table>
    <tr>
        <td>
            <a href="https://imgur.com/dQzufRF"><img src="https://i.imgur.com/dQzufRF.jpg" title="source: imgur.com"  Height = "250" width="350"/></a>
        </td>
        <td>
            <a href="https://imgur.com/0MQp4eg"><img src="https://i.imgur.com/0MQp4eg.jpg" title="source: imgur.com"  Height = "250" width="350" /></a>
        </td>
        <td>
            <a href="https://imgur.com/A6KGpsn"><img src="https://i.imgur.com/A6KGpsn.jpg" title="source: imgur.com" Height = "250" width="350" /></a>
        </td>
    </tr>
</table>



<!-- #endregion -->

```sql azdata_cell_guid="af13eabb-817a-4288-857c-4cb41c40eb59"
-- Character
DECLARE @myChar CHAR(20) = 'Edvancer'
SELECT @myChar AS Char, DATALENGTH (@myChar) as Datalength, LEN(@myChar) AS Len
```

```sql azdata_cell_guid="178ce8c2-5ace-4054-adf9-7da75e513087"
-- Varchar
DECLARE @myChar VARCHAR(20) = 'Edvancer'
SELECT @myChar AS Varchar, DATALENGTH (@myChar) as Datalength, LEN(@myChar) AS Len
```

<!-- #region azdata_cell_guid="d07b107f-7d42-49cb-bd8b-7f79e7f3f881" language="" -->
# Numeric Datatype

<table>
    <tr>
        <td>
            <a href="https://imgur.com/3LaZhsZ"><img src="https://i.imgur.com/3LaZhsZ.jpg" title="source: imgur.com" Height = "250" width="350"/></a>
        </td>
        <td>
            <a href="https://imgur.com/UwyAX8u"><img src="https://i.imgur.com/UwyAX8u.jpg" title="source: imgur.com" Height = "250" width="350" /></a>
        </td>
        <td>
            <a href="https://imgur.com/0QLcLq5"><img src="https://i.imgur.com/0QLcLq5.jpg" title="source: imgur.com" Height = "250" width="350" /></a>
        </td>
    </tr>
</table>
<!-- #endregion -->

```sql azdata_cell_guid="c424750d-3dd1-4d13-a915-fbd9709bea20" tags=[]
DECLARE @num NUMERIC(7,2) = 12376.7854
SELECT @num as NumericData
```

```sql azdata_cell_guid="83fbe8b4-bc23-4239-a5b8-f4934d542360" tags=["hide_input"]
DECLARE @SmallInt SMALLINT = 12376.7854
SELECT @SmallInt AS SmallIntData
```

```sql azdata_cell_guid="1f7898ac-be94-412a-825c-1e6630184335"
-- DECLARE @SmallInt SMALLINT = -32769 
-- SELECT @SmallInt AS SmallIntData
-----------------Errors when we un comment above and run codes
-- if we give more/less than 
--affordable range it will gives an error
--Msg 220, Level 16, State 1, Line 1
--Arithmetic overflow error for data type smallint, value = -32769.
```

```sql azdata_cell_guid="9b3428c4-b36b-4675-838e-28a68c43b8a7" tags=[]
DECLARE @TinyInt SMALLINT = 254
SELECT @TinyInt AS TinyIntData
```

<!-- #region azdata_cell_guid="b711750f-25d1-48ea-911e-de5f800c7e00" language="" -->
<table>
    <tr>
        <td>
            <a href="https://imgur.com/4gbEnje"><img src="https://i.imgur.com/4gbEnje.jpg" title="source: imgur.com" Height = "250" width="350"/></a>
        </td>
        <td>
            <a href="https://imgur.com/M3gfFAN"><img src="https://i.imgur.com/M3gfFAN.jpg" title="source: imgur.com" Height = "250" width="350" /></a>
        </td>
        <td>
            
        </td>
    </tr>
</table>
<!-- #endregion -->

```sql azdata_cell_guid="8ec9ee65-91ea-4228-9aa0-2d3a3a81ff0c"
--Float
DECLARE @float FLOAT(10) = 12376.7854
SELECT @float as FLOAT

```

```sql azdata_cell_guid="4e522468-5178-4660-be70-7fbc201ac577"
--Data type precedence
DECLARE @float1 FLOAT(10), @int INT
SET @float1 = 12376.7854
SET @int = 570
SELECT @float1 + @int as Result
```

<!-- #region language="sql" azdata_cell_guid="35960561-94b1-49b8-8d4d-6e2e7438a8f3" -->
# Filter the data using where
<!-- #endregion -->

<!-- #region language="sql" azdata_cell_guid="81459037-3625-450c-ac8b-93661d1ffc48" -->

<!-- #endregion -->

```sql azdata_cell_guid="66e8a856-62af-4764-a6ca-44686622562f" tags=[]
SELECT * from HumanResources.Employee WHERE SickLeaveHours > 50;
SELECT * from Sales.CreditCard WHERE ExpYear = 2008;
```

```sql azdata_cell_guid="77641d4f-7584-402b-b3f8-b903d1638477"
USE Training
```

```sql azdata_cell_guid="d0342d31-a6f3-4dea-9d48-a15605f4bbac"
-- selecting products table
SELECT * FROM products;
```

```sql azdata_cell_guid="c9177609-3c86-47d7-93d4-a070b61f09ed" tags=[]
-- selecting city table
SELECT * FROM city;
```

```sql azdata_cell_guid="c825ca35-b352-41a2-9ec9-db6e62f6c3e5"
SELECT * from City;
```

```sql azdata_cell_guid="064d86e9-15ca-435c-a161-3cbdf665fff3"
Use Training;
```

```sql azdata_cell_guid="5bbe5240-984e-4ec7-a6d4-860e3f81ff52"
SELECT * 
from City where populationDensity = 'High';

```

```sql azdata_cell_guid="1c141a8b-e26f-4c7d-9a12-1db4cf855e1c"
SELECT *
  FROM City WHERE PopulationDensity = 'High'
```

<!-- #region language="sql" azdata_cell_guid="40214dbf-376a-4c9c-8192-5b1c8ce1371b" -->

<!-- #endregion -->

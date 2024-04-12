# UberDataSQL
### 🌱 Project Description 
This project explores **[Uber's stock data from 2019-2022](https://www.kaggle.com/datasets/varpit94/uber-stock-data/data)** using **SQL**. 

### Schema
![Schema Photo](https://github.com/Aaronsupa/UberDataSQL/assets/77075455/4bf28bc7-b058-4fd4-bba9-1623a051c3ce)

### Exploring the Data
- Query to see the top 5 highest volume entries 
```
select * from data order by volume desc limit 5;
```
**output:**

|    Date    |   Open   |   High   |    Low    |  Close   | Adjusted Close |   Volume    |
|------------|----------|----------|-----------|----------|----------------|-------------|
| 2019-05-10 | 42.0     | 45.0     | 41.060001 | 41.57    | 41.57          | 186322500   |
| 2019-11-06 | 26.059999| 27.549999| 25.58     | 26.940001| 26.940001      | 130965700   |
| 2022-02-10 | 41.0     | 42.560001| 37.349998 | 37.75    | 37.75          | 113915000   |
| 2020-02-07 | 39.98    | 41.0     | 38.860001 | 40.630001| 40.630001      | 112325800   |
| 2021-09-21 | 42.34    | 45.0     | 42.18     | 44.360001| 44.360001      | 106631700   |


- Query to see the highest volume day in 2019
```
create table data_2019 as select * from data where date > '2018-12-31' and date < '2020-01-01';
select * from data_2019 order by volume desc limit 1;
```
**output:**

|   date     |  open  |  high  |   low    |  close  | adjusted_close |   volume   |
|------------|--------|--------|----------|---------|----------------|------------|
| 2019-05-10 |   42   |   45   | 41.060001|  41.57  |      41.57     | 186322500  |


- Query to see the day where the high was furthest from the low
```
select date, ABS(high - low) as difference from data order by difference desc limit 1;
```
**output:**

|    date    |     difference     |
|------------|--------------------|
| 2021-04-29 | 6.1100000000000065 |


- Query to see the day where the open was furthest from the close
```
select date, ABS(open - close) as difference from data order by difference desc limit 1;
```
**output:**

|    date    |     difference     |
|------------|--------------------|
| 2022-02-24 |  4.899999999999999 |


### Technologies Used 
- 🗄️ SQL
- 💻 DataGrips
- 📊 Excel

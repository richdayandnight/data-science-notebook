---
title: PySpark
created: '2022-01-18T07:32:08.970Z'
modified: '2022-01-18T07:48:49.072Z'
---

# PySpark

Notes from this [video](https://www.youtube.com/watch?v=_C8kWso4ne4)

- Start a session
```
from pyspark.sql import SparkSession

spark = SparkSession.builder.appName("App Name").getOrCreate()
```
- Read a file
```
spark.read.csv("filepath.csv")
```
- Read a file including options
```
df_pyspark = spark.read.option("header", "true").csv("filepath.csv")
```
- Show a pyspark dataframe
```
df_pyspark.show()
```
- Type of pyspark dataframe
```
type(df_pyspark)
---
pyspark.sql.dataframe.DataFrame
```
- Check and prtiny the Datatypes of the columns (Similar w/ pandas.info())
```
df_pyspark.printSchema()
---
root
 |-- YEAR: integer (nullable = true)
 |-- MOVIE: string (nullable = true)
 |-- GENRE: string (nullable = true)
 |-- MPAA RATING: string (nullable = true)
 |-- DISTRIBUTOR: string (nullable = true)
 |-- TOTAL FOR YEAR: integer (nullable = true)
 |-- TOTAL IN 2019 DOLLARS: integer (nullable = true)
 |-- TICKETS SOLD: integer (nullable = true)

```
- Selecting Columns and Indexing
```
# single column
df_pyspark.select("TICKETS SOLD").show()
# multiple columns
df_pyspark.select(["MOVIE", "TICKETS SOLD"]).show()
# 3 rows
df_pyspark.head(3)
```
- Check Describe option similar to Pandas
```
df_pyspark.describe().show()
---
Output: table containing count, mean, stddev, min, and max
```
- Adding Columns
```
df_pyspark = df_pyspark.withColumn('TEST', df_pyspark["TICKETS SOLD"]*2)
```
- Dropping columns
```
df_pyspark = df_pyspark.drop("TEST")
```


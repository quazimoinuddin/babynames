--------------- Replace "source_link" with the direct link to your Parquet file
source_link = "https://raw.githubusercontent.com/toddwschneider/nyc-taxi-data/master/data/central_park_weather.csv"
 
---------------- Replace "dbfs_path" with the desired path in DBFS
dbfs_path = "/dbfs/data/central_park_weather.csv"
 
----------------- Download the file and write it to DBFS
dbutils.fs.cp(source_link, dbfs_path)
 
df = spark.read.option("header", True).csv("/dbfs/data/central_park_weather.csv")

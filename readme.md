##SPARK REPL Commands

val file = spark.read.option("header", "true")
.option("inferSchema", "false").csv("...");

file.printSchema()

file.write.mode(SaveMode.Append).parquet("...");

data.createOrReplaceTempView("data");
spark.sql("""select * from data ...""").show();


#####Min, max, mean, standard deviation
val summary = data.describe();
summary.show();
summary.select("CITY").show();

val albania = data.where($"COUNTRY" === "ALBANIA");
albania.show();
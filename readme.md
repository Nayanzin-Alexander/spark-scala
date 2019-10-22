##SPARK REPL Commands

val file = spark.read.option("header", "true")
.option("inferSchema", "false").csv("...");

file.write.mode(SaveMode.Append).parquet("...");

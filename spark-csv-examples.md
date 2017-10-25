val spark = SparkSession
      .builder()
      .appName("Java Spark SQL basic example")
      .config("spark.master", "local")
      .getOrCreate()

    import spark.implicits._

    val csvDS = spark.read.format("com.databricks.spark.csv")
      .option("header", "true")
      .option("inferSchema","true")
      .load("/home/hduser/RAMA/emp.csv")
      .as[Emp]

    csvDS.show()
    csvDS.printSchema()

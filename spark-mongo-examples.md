    //changing dataframe column values to upper case

    df3.registerTempTable("emp")
    df3.sqlContext.sql("select empId,upper(empName) as empName,salary from emp")
      .filter($"salary">1000).show
    df3.show()
	
    //****** or *******
	
     df3.select($"empName",upper($"empName")).show()
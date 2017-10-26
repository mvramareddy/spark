    //filtering dataFrame 
    
     df.filter($"salary">500 && $"salary"<1000)	
 
    // or
	
	df.filter("salary> 500 AND salary <1000")
	
	//changing dataframe column values to upper case
	
    df.registerTempTable("emp")
    df.sqlContext.sql("select empId,upper(empName) as empName,salary from emp")
      .show
    df.show()
	
    // or
	
     df.select($"empName",upper($"empName")).show()
	 

	
	
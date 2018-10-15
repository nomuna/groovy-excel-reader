groovy-excel-reader
===================

Utility groovy class to read MS Excel xlsx documents

Based on Goran Ehrsson's post: http://www.technipelago.se/content/technipelago/blog/44.  
Modified Goran's code to handle xlsx document types, and just return the string formatted value of each cell (ignore types).


Usage examples
==============

## Fill a bean with data from rows

```groovy
new ExcelBuilder("customers.xls").eachLine([labels:true]) {
  new Person(name:"$firstname $lastname",
    address:address, telephone:phone).save()
}
```

## Accessing cells using indexes

```groovy
new ExcelBuilder("customers.xls").eachLine {
  println "First column on row ${it.rowNum} = ${cell(0)}"
}
```


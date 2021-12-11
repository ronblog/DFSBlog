SQL tips about QueryBook and Druid board


1， use single quotation mark not double quotation mark in where condition statement
Like "metricName" <> 'msg', the first double quotation mark is OK, but the double quotation mark will not work in the second quotation.

2, alias can be the column's title but alias is not used in the group by  statement.
Like DT, Total are column title, but DT, Total can’t use in group by statement

3, time function, from long to date time;
DATE_TRUNC('hour',MILLIS_TO_TIMESTAMP(PARSE_LONG( "timestamp"  ) ) )

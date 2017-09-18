---
layout: post
title: 'Create a dynamic calendar in MS SQL'
author: Lucas Callado
categories:
  - Database
---
# Create a dynamic calendar in MS SQL

<pre class="height-set:true height:350 lang:mysql decode:true ">----- MS SQL: Simple way to build a calendar passing the month and the year. -----

DECLARE @intMonth tinyint          
DECLARE @intYear int  

SET @intMonth = 1;
SET @intYear = 2015;       

DECLARE @dtPrevMonth DATETIME
DECLARE @dtNextMonth DATETIME
DECLARE @dtMonth DATETIME
DECLARE @dtLastDay DATETIME
DECLARE @lastWeekDay INT
DECLARE @firstWeekDay INT
DECLARE @calStartDate DATETIME
DECLARE @calEndDate DATETIME
DECLARE @dayCalStartDate INT
DECLARE @dayCalEndDate INT

SELECT @dtMonth = CAST(CAST(@intYear AS VARCHAR(4)) + '/' + CAST(@intMonth AS VARCHAR(2)) + '/1' AS DATETIME)
	,@dtPrevMonth = DATEADD(month, -1, @dtMonth)
	,@dtNextMonth = DATEADD (month , 1, @dtMonth)
	,@dtLastDay = DATEADD (day , -1, @dtNextMonth)
	,@lastWeekDay = DATEPART(WEEKDAY, @dtLastDay)
	,@firstWeekDay = DATEPART(WEEKDAY, @dtMonth)
	,@calStartDate = DATEADD (day , 1-@firstWeekDay, @dtMonth)
	,@calEndDate = DATEADD (day , 7-@lastWeekDay, @dtLastDay)
	,@dayCalStartDate = DATEPART(DAYOFYEAR, @calStartDate)
	,@dayCalEndDate = DATEPART(DAYOFYEAR, @calEndDate);

	DECLARE @calendarTemp TABLE          
		(
		datedd datetime
		);

	WITH CTE_DatesTable (datedd)
		AS
		(
		SELECT @calStartDate AS datedd          
		UNION all
		SELECT DATEADD(dd, 1, datedd)
		FROM CTE_DatesTable
		WHERE DATEADD(dd, 1, datedd) &lt;= @calEndDate
		)

 SELECT           
	m.datedd
	,DATEPART(WEEKDAY, m.datedd) AS dayofweeknum             
 FROM CTE_DatesTable m          
 ORDER BY m.datedd

  SELECT           
	@intYear AS currentYear          
	,@intMonth AS currentMonth          
	,@dtPrevMonth AS prevMonth          
	,@dtNextMonth AS nxtMonth          
	,@dtMonth AS  firstDateCurrentMonth          
	,@dtLastDay AS lastDateCurrentMonth          
	,@lastWeekDay AS lastDayCurrentMonth          
	,@firstWeekDay AS firstDayCurrentMonth          
	,@calStartDate AS calStartDate          
	,@calEndDate AS calEndDate          
	,@dayCalStartDate AS dayCalStartDate          
	,@dayCalEndDate AS dayCalEndDate;          
</pre>

First result set will give you a two-week period, and the day of the week for each date.

Second result set will give more information like:

  * Previous month
  * Next month
  * First day of month
  * Last day of month
  * Day of the week for first day of the month
  * Day of the week for last day of the month
  * Calendar week start date
  * Calendar week last date
  * Day of the calendar for the start date
  * Day of the calendar for the last date

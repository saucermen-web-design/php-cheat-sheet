Date and Time

# Date and Time

* `date()` function formats a timestamp to a more readable date and time.

	* Syntax

		* `date(format,timestamp)`

| Parameter | Description |
| :------------- | -----------: |
| format | Required. Specifies the format of the timestamp |
| timestamp | Optional. Specifies a timestamp. Default is the current date and time |
<br />

## Get a Date

* The required format parameter of the date() function specifies how to format the date (or time).

* Here are some characters that are commonly used for dates:
<br/>

| Character | Description |
| :---- | -----------: |
| d | Represents the day of the month (01 to 31) |
| m | Represents a month (01 to 12) |
| Y | Represents a year (in four digits) |
| l (lowercase 'L') | Represents the day of the week |
<br />

* Other characters, like"/", ".", or "-" can also be inserted between the characters to add additional formatting.

#### Auto Copyright year: `&copy; 2010-<?php echo date("Y");?>`

## Get a Time

* Here are some characters that are commonly used for times:

| Character | Description |
| :---- | -----------:|
| H | 24-hour format of an hour (00 to 23) |
| h | 12-hour format of an hour with leading zeros (01 to 12) |
| i | Minutes with leading zeros (00 to 59) |
| s | Seconds with leading zeros (00 to 59) |
| a | Lowercase Ante meridiem and Post meridiem (am or pm) |

#### Note that the PHP `date()` function will return the **current** date/time of the **server**!

## Get Time Zone

* If you need the time to be correct according to a specific location, you can set the timezone you want to use.

* The example below sets the timezone to "America/New_York", then outputs the current time in the specified format:

```
<?php
date_default_timezone_set("America/New_York");
echo "The time is " . date("h:i:sa");
?>
```

## Create Date With `mktime()`

* The optional timestamp parameter in the `date()` function specifies a timestamp. 
	
	* If omitted, the current date and time will be used (as in the examples above).

* The PHP `mktime()` function returns the Unix timestamp for a date. 

	* The Unix timestamp contains the number of seconds between the Unix Epoch (January 1 1970 00:00:00 GMT) and the time specified.

		* Syntax

			* `mktime(hour, minute, second, month, day, year)`

## Create Date From String With strtotime()

* The PHP `strtotime()` function is used to convert a human readable date string into a Unix timestamp (the number of seconds since January 1 1970 00:00:00 GMT).

	* Syntax
	
		* `strtotime(time, now)`

* PHP is quite clever about converting a string to a date, so you can put in various values:

	* Example:

```
<?php
$d=strtotime("tomorrow");
echo date("Y-m-d h:i:sa", $d) . "<br>";

$d=strtotime("next Saturday");
echo date("Y-m-d h:i:sa", $d) . "<br>";

$d=strtotime("+3 Months");
echo date("Y-m-d h:i:sa", $d) . "<br>";
?>
```

* However, strtotime() is not perfect, so remember to check the strings you put in there.
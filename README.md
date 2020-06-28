# JavaIntDatesConverter
Convert calendar date to/from int (Excel&reg;) date using plain old, lightning fast, integer arithmetics.

## What is the int (Excel&reg;) date?

The int (Excel&reg;) date is the number of days since the beginning of 1900, with a few considerations:

* Day 0 is, somehow, January the 0<sup>th</sup>, 1900 (&#x2724;)
* Day 1 is January the 1<sup>st</sup>, 1900
* Day 60 is February the 29<sup>th</sup>, 1900 (&sext;)
* Day 61 is Thursday, March the 1<sup>st</sup>, 1900. Since that day everything is normal and correct

&#x2724;: Day 0 is generally used as a default date, meaning ``no date specified´´.

&sext;: 1900 was **not** a leap year, but Lotus123 considered it a leap year by mistake. Microsoft&reg; Excel&reg; perpetuates that tradition for backward compatibility.

You can play wit this conversion in Microsoft&reg; Excel&reg;:
* Write a number in a cell, and then change the cell format to short date.
* Write a date in a cell, and then change the cell format to number.

## Application examples

#### Problem 1: What's my exact age in days?

Let's say that I was born on February the 20<sup>th</sup>, 2000 &mdash;not my real birth date, but I do feel that young!&mdash;. That was day 36576.

Well, today is June the 28<sup>th</sup>, which is day 44010.

44010 - 36576 = **7434**. That would be my age in days!! Easy, isn't it?

#### Problem 2: How many days do I have to buy a new suit or loose 5Kg?

My friends Alice and Bob are going to get married on May, the 22<sup>nd</sup>, 2021. That's day 44366. As I said, today is day 44010...

I have 44338 - 44010 = **328** days. It seems a long time. In theory I could loose those 5Kg. But if we consider Christmas, birthday parties... I'd better make plans to buy a new suit in April!

#### Problem 3: When will Unix time end?

[Unix time](https://en.wikipedia.org/wiki/Unix_time) started on January the 1<sup>st</sup>, 1970, which is day 25569.

It will last 2<sup>32</sup> = 4294967296 seconds. The number of seconds per day is 24 * 60 * 60 = 86400. Therefore, Unix time lasts 4294967296 / 86400 &asymp; 49710.27 days.

25569 + 49710 = 75279, which is **February the 7<sup>th</sup>, 2106**, early in the morning. Don't count on me for that apocalypse. I don't feel *that* young.

Oh, but this is only valid if you consider the 32 bits unsigned! If it is treated as a signed 32-bits number, the overflow occurs at 2<sup>31</sup> seconds since the beginning of 1970. That leads to... 25569 + 49710<b>/2</b> = 50424, which is **January the 19<sup>th</sup>, 2038**. Oh my!

Don't worry about that, though. The world will end even sooner. [Network Time Protocol timestamps](https://en.wikipedia.org/wiki/Network_Time_Protocol#Timestamps) will experience their 32 bit (unsigned) overflow on February the 7<sup>th</sup>, 2036. That's exactly 70 years earlier than the overflow of the unsigned Unix time because NTP timestamps are based on year 1900 instead of 1970 &mdash;but I digress.

[//]: # (#### Problem 4: //--MKR TODO: week day...)

[//]: # (## Alternatives //--MKR TODO: Mention other ways to do the translation and explain why this library is better)

## For more details, see:

* The javadoc [documentation](https://mkrevuelta.github.io/JavaIntDatesConverter/docs/index.html).
* The [project page](https://github.com/mkrevuelta/JavaIntDatesConverter) in GitHub.

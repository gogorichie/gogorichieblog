---
title: "Using DateDiff to Control Content"
date: 2010-10-20
draft: false
summary: ""
summaryImage: ""
tags: ["SQL"]
---


Last Friday I got a data request from a group asking for a report to be generated bi-hourly for customer request that were not responded to in a time span of two hours. So looking at the data I noticed that there were two columns that were time stamped one when the request was submitted and another when the request was completed, so this was easy I filtered out where the completed data was null and wrote a where statement using a Datediff syntax to breakdown the input date time stamp by hour and then subtracting two so my sql statement looks like the following example.

--------------------------------------------------------------------------------------------------------------

<span style="color: #800000;">SELECT recID, inputDateTime, customername, phonenumber, address, emailaddress, requestcomment  
FROM      dbo.VIEW_CustomerOrders_SCRUB  
WHERE  (DATEDIFF(hh, inputDateTime, GETDATE()) = 2)</span>

--------------------------------------------------------------------------------------------------------------

Now if you wanted to change it up and make the date two days instead of hours you could easily change the hh argument to dd and so fourth. On the MSDN page from Microsoft they do a good job at covering how to use the datediff arguments to get different results. [http://msdn.microsoft.com/en-us/library/ms189794(v=SQL.90).aspx](http://msdn.microsoft.com/en-us/library/ms189794(v=SQL.90).aspx)
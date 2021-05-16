---
title: "Stupid Duplicates Die Won’t You"
date: 2010-07-24
draft: false
summary: ""
summaryImage: ""
tags: ["SQL"]
---


So the other day my former team member call me asking for help. She had inserted the same data into a table three or more times and needed to get rid of them. For those of you with duplications and need to delete them here’s a little statement i came up with and gave her.

DELETE FROM TBL_Employees

WHERE     (EmpID IN

                          (SELECT     MAX(EmpID) AS Expr2

                            FROM          TBL_Employees

                            GROUP BY FirstName

                            HAVING      (COUNT > 1)))
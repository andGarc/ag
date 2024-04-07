+++
title = 'Useful Tableau Calculations'
date = 2023-08-14
draft = false
tags = ['tableau']
ShowToc = true
+++

## Dates

Max Date  
`MONTH([Date]) = MONTH({ FIXED : MAX([Date])})`

Max Date where values is not null or 0  
`[Date] = { FIXED : MAX(IF [Actual Miles] <> 0 THEN [Date] END)}`

Get previous date using max date  
`{ FIXED : MAX(IF [Max Date] = FALSE THEN [Date] END) }`

Get previous value using previous date  
`IF [Date] = [Previous Date] THEN [MPG] ELSE 0 END`

Get current value using max date  
`IF [Max Date] = TRUE THEN [MPG] ELSE 0 END`

## Category
Get the category for a max value  
1. Get the max value for every category
	`{ FIXED [Year], [State] : MAX([CandidateVotes]) }`
2. Compare max value to individual value and return category
	`IF [CandidateVotes] = [Max Votes Year State] THEN [Part Simplified Abbrv] END`

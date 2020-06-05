# splunk
  `index=sab* source="/WAS/tracelog" UsageInfo
  |rex field=_raw "\[(?<timestamp>[^[]*)\]\s"
  |table timestamp`
 
 all index
 
 `index=* | dedup index | table index`

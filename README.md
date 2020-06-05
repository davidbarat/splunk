# splunk
  `index=sab* source="/WAS/tracelog" UsageInfo
  |rex field=_raw "\[(?<timestamp>[^[]*)\]\s"
  |table timestamp`
 
 all index
 `index=* index=_* | dedup index | fields index | rest /services/data/indexes | dedup title | table title`

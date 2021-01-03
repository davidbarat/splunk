# splunk
  `index=sab* source="/WAS/tracelog" UsageInfo
  |rex field=_raw "\[(?<timestamp>[^[]*)\]\s"
  |table timestamp`
 
 all index
 
 `index=* | dedup index | table index`
 
 all sources
 
 `index=* |dedup source |chart count by source`
 
 `your base search | rex field=_raw (?<src>\d+\.\d+\.\d+\.\d+).+\]\s\"(?<http_method>\w+)\s(?<uri_path>.+)\"\s(?<status>\d+)`

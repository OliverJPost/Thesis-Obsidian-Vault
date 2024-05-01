# Analysis
![[_Analysis Canvas.canvas|_Analysis Canvas]]
The analysis phase goes through the following steps sequentially:
1. [[Download data]]
2. [[Process data]]
3. [[Cluster data]]
4. [[Analyze data]]
5. [[Export profiles]]

```dataviewjs
var reftab = require(app.vault.adapter.basePath + "/_Vault/reftab.js");
 
reftab.referenceTable(dv, ['#type/reference', '#step/analysis'])
```
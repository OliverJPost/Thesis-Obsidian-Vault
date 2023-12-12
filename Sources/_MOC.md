## References
```dataview
TABLE 
	filter(file.tags, (t) => t != "#type/reference" AND t !="#type") as "Tags",
	keywords as "Keywords",
	importance as "Imp.",
	choice(completed , "✅", "✘") as "Comp."
FROM #type/reference
```

## Implementations
```dataview
TABLE 
	filter(file.tags, (t) => t != "#type/implementation" AND t !="#type") as "Tags",
	importance as "Imp.",
	choice(completed , "✅", "✘") as "Comp."
FROM #type/implementation
```

## Data
```dataview
TABLE 
	filter(file.tags, (t) => t != "#type/data" AND t !="#type") as "Tags",
	importance as "Imp.",
	choice(completed , "✅", "✘") as "Comp."
FROM #type/data
```

## Utilities
```dataview
TABLE 
	filter(file.tags, (t) => t != "#type/utility" AND t !="#type") as "Tags",
	importance as "Imp.",
	choice(completed , "✅", "✘") as "Comp."
FROM #type/utility
```
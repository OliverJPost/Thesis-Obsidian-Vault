# Data Sources
```dataviewjs
let tag = "#type/data";


// Load dataview plugin
dv.table(
  ["Title", "Thumbnail", "Imp."], 
  dv.pages(tag)
    .map(page => [
      // Prepend the result of determineRead to the title
      `${determineRead(page.file.tags)}${page.aliases && page.aliases.length > 0 ? `[${page.aliases[0]}](${page.file.path})` : `[${page.file.name}](${page.file.path})`}`, 
      page.thumb ? 
        dv.span(`${page.thumb}`, {style: "width: 50px; height: auto; display: inline-block;"}) : 
        "", // Display the thumbnail if exists, resized
      determineImportance(page.file.tags) // Custom function to determine importance based on emoji in tags
      
    ])
);

function determineImportance(tags) {
  if (tags.includes('#💎')) return "💎Extreme";
  else if (tags.includes('#🔵')) return "🔵High";
  else if (tags.includes('#🔸')) return "🔸Medium";
  else if (tags.includes('#🔻')) return "🔻Low";
  else return "Undefined";
}

function determineRead(tags) {
  if (tags.includes('#✅')) return "✅ ";
  else return '';
}


```

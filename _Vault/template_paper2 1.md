---
citekey: {{citekey}}
aliases: ["
    {%- if creators -%}
        {{creators[0].lastName}}
        {%- if creators|length > 1 %} et al.{% endif -%}
    {%- endif -%}
    {%- if date %} ({{date | format("YYYY")}}){% endif -%} 
    {%- if shortTitle %} {{shortTitle | safe}} {%- else %} {{title | safe}} {%- endif -%}
"]
title: "{{title}}"
authors: {{authors}}
tags: [literature-note, {% for t in tags %}{{t.tag}}{% if not loop.last %}, {% endif %}{% endfor %}]
year: {{date | format("YYYY")}}
publisher: "{{publicationTitle}}"
doi: {{DOI}}
---
{% macro formatCell(cellText) -%}
{{ cellText | replace("|","❕")}}
{%- endmacro %}
{#- TAGS: handle space characters in zotero tags -#}
{%- set space = joiner(' ') -%}
{%- macro printTags(rawTags) -%}
{%- if rawTags.length > 0 -%}
{%- for tag in rawTags -%}
#{{ tag.tag | lower | replace(" ","_") }} {{ space() }}
{%- endfor -%}
{%- endif -%}
{%- endmacro %}
# [{{title}}]({{desktopURI}})

{% persist "notes" %}
{% if isFirstImport %}
## Key takeaways
- 

## Processing

- **Status**:: <% tp.file.cursor(2) %>
- **Priority**:: <% tp.file.cursor(3) %>
{% endif %}{% endpersist %}

> [!info]- Info - [**Zotero**]({{desktopURI}}) | [**DOI**](https://doi.org/{{DOI}}) | {% for attachment in attachments | filterby("path", "endswith", ".pdf") %}[**PDF**](file:///{{attachment.path | replace(" ", "%20")}}){%- endfor %}
>
> {% if bibliography %}**Bibliography**: {{bibliography|replace("\n"," ")}}{% endif %}
> 
> **Authors**:: {% for a in creators %} [[{{a.firstName}} {{a.lastName}}]]{% if not loop.last %}, {% endif %}{% endfor %}
> 
> {% if hashTags %}**Tags**: {{hashTags}}{% endif %}
> 
> **Collections**:: {% for collection in collections %}[[{{collection.name}}]]{% if not loop.last %}, {% endif %}{% endfor %}
> 
> **First-page**: {% for annotation in annotations %}{% if loop.first %}{{annotation.pageLabel}}{% endif %}{% endfor %}

> [!abstract]-
> {% if abstractNote %}
> {{abstractNote|replace("\n"," ")|striptags(true)|replace("Objectives", "**Objectives**")|replace("Background", "**Background**")|replace("Methodology", "**Methodology**")|replace("Results","**Results**")|replace("Conclusion","**Conclusion**")}}
> {% endif %}

{%- if relations.length > 0 %}
{{ "" }}
> [!abstract]- Related Zotero items ({{ relations.length}}):  
>
> | title | proxy note | desktopURI |
> | --- | --- | --- |
{%- for r in relations %}
> | {{formatCell(r.title)}} | [[@{{r.citekey}}]] | [Zotero Link]({{r.desktopURI}}) | {% if rel.DOI %}> DOI: {{rel.DOI}}{% endif %} |
{%- endfor -%}
{{ "" }}
{%- endif %}

{% if notes.length > 0 %}
> [!note] Notes ({{notes.length}})
{{ "" }}
{%- for note in notes -%}
{#- Clean up note, change heading level, just in case -#}
> {{ note.note | replace ("# ","### ") | replace(r/\n/g, '\n> ')}}
> {{printTags(note.tags)}}
> <small>📝️ (modified: {{ note.dateModified | format("YYYY-MM-DD") }}) [link](zotero://select/library/items/{{note.key}}) - [web]({{note.uri}})</small>
>  {{ "" }}
> ---
{% endfor %}
{% endif -%}

> [!quote]- Citations
> 
> ```query
> content: "@{{citekey}}" -file:@{{citekey}}
> ```
 
---

## Reading notes
{% macro heading(color) -%}
{%- if color == "#5fb236" -%}
💡 Main ideas and conclusions
{%- endif -%}
{%- if color == "#2ea8e5" -%}
❔ Questions
{%- endif -%}
{%- if color == "#ffd400" -%}
⭐ Important
{%- endif -%}
{%- if color == "#a28ae5" -%}
🧩 Definitions and concepts
{%- endif -%}
{%- if color == "#ff6666" -%}
⛔ Weaknesses and caveats
{%- endif -%}
{%- if color == "#e56eee" -%}
⚡ Hypotheses
{%- endif -%}
{%- if color == "#f19837" -%}
⚙️ Method
{%- endif -%}
{%- if color == "#aaaaaa" -%}
📣 Survey instruments
{%- endif -%}
{%- endmacro -%}

{% macro calloutCharacter(color) -%}
{%- if color == "#5fb236" -%}
$
{%- endif -%}
{%- if color == "#2ea8e5" -%}
@
{%- endif -%}
{%- if color == "#ffd400" -%}
&
{%- endif -%}
{%- if color == "#a28ae5" -%}
~
{%- endif -%}
{%- if color == "#ff6666" -%}
!
{%- endif -%}
{%- if color == "#e56eee" -%}
€
{%- endif -%}
{%- if color == "#f19837" -%}
?
{%- endif -%}
{%- if color == "#aaaaaa" -%}
%
{%- endif -%}
{%- endmacro -%}

{% persist "annotations" %}
{% set annotations = annotations | filterby("date", "dateafter", lastImportDate) -%}
{% if annotations.length > 0 %}
*Imported on {{importDate | format("YYYY-MM-DD HH:mm")}}*

{% for color, annotations in annotations | groupby("color") -%}

### {{heading(color)}} %% fold %%
{% for annotation in annotations -%}
{%- if annotation.imageRelativePath %}

> [!cite]+ Image [(p. {{annotation.pageLabel}})](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}})
> ![[{{annotation.imageRelativePath}}]]{% if annotation.hashTags %}
> {{annotation.hashTags}}{% endif %}{%- if (annotation.comment or []).indexOf("todo ") !== -1 %}
> - [ ] **{{annotation.comment | replace("todo ", "")}}**{% else %}
> **{{annotation.comment}}**{%- endif -%}

{% elif (annotation.comment or []).indexOf("todo ") !== -1 %}
- [ ] **{{annotation.comment | replace("todo ", "")}}**:{% if not annotation.annotatedText %} [(p. {{annotation.pageLabel}})](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}){% else %}
	- {{calloutCharacter(annotation.color)}} {{annotation.annotatedText | nl2br}} [(p. {{annotation.pageLabel}})](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}) {% if annotation.hashTags %}{{annotation.hashTags}}{% endif -%}{% endif -%}
{% elif annotation.comment %}
- **{{annotation.comment}}**:{% if not annotation.annotatedText %} [(p. {{annotation.pageLabel}})](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}){% else %}
	- {{calloutCharacter(annotation.color)}} {{annotation.annotatedText | nl2br}} [(p. {{annotation.pageLabel}})](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}) {% if annotation.hashTags %}{{annotation.hashTags}}{% endif -%}{% endif %}
{%- elif annotation.annotatedText %}
- {{calloutCharacter(annotation.color)}} {{annotation.annotatedText | nl2br}} [(p. {{annotation.pageLabel}})](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}) {% if annotation.hashTags %}{{annotation.hashTags}}{% endif %}
{%- endif -%}{%- endfor %}

{% endfor -%}
{% endif %}
{% endpersist %}


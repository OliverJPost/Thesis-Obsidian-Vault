---
aliases: ["
    {%- if creators -%}
        {{creators[0].lastName}}
        {%- if creators|length > 1 %} et al.{% endif -%}
    {%- endif -%}
    {%- if date %} ({{date | format("YYYY")}}){% endif -%} 
    {%- if shortTitle %} {{shortTitle | safe}} {%- else %} {{title | safe}} {%- endif -%}
"]
tags: [{% for t in tags %}{{t.tag}}{% if not loop.last %}, {% endif %}{% endfor %}]
year: {%- if date %} {{ date | format("YYYY")}}{% else %} {% endif %}
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
{%- endmacro %}# {{title}} [📖]({{desktopURI}})

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

{% persist "notes" %}
{% if isFirstImport %}![[image.png | canvas-top]]
## Permanent notes
importance::undefined
completed::false
### Initial thoughts:


### Relations:


### Summary


{% endif %}{% endpersist %}
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
Imported on {{importDate | format("YYYY-MM-DD HH:mm")}}


{% for annotation in annotations -%}
{% if (annotation.color == "#e56eee") %}
### {{annotation.annotatedText}}
{% else %}
{%- if annotation.imageRelativePath %}

- {{calloutCharacter(annotation.color)}} **{{annotation.comment}}** {% if annotation.hashTags %}{{annotation.hashTags}}{% endif %} [(p. {{annotation.pageLabel}})](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}) ![[{{annotation.imageRelativePath}}]]
{%- if (annotation.comment or []).indexOf("todo ") !== -1 %}
- [ ] **{{annotation.comment | replace("todo ", "")}}**{% endif %}

{% elif (annotation.comment or []).indexOf("todo ") !== -1 %}
- [ ] **{{annotation.comment | replace("todo ", "")}}**:{% if not annotation.annotatedText %} [(p. {{annotation.pageLabel}})](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}){% else %}
	- {{calloutCharacter(annotation.color)}} {{annotation.annotatedText | nl2br}} [(p. {{annotation.pageLabel}})](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}) {% if annotation.hashTags %}{{annotation.hashTags}}{% endif -%}{% endif -%}
{% elif annotation.comment %}
{% if not annotation.annotatedText %}- **{{annotation.comment}}** [(p. {{annotation.pageLabel}})](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}){% else %}- {{calloutCharacter(annotation.color)}} {{annotation.annotatedText | nl2br}} [(p. {{annotation.pageLabel}})](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}) **{{annotation.comment}}** {% if annotation.hashTags %}{{annotation.hashTags}}{% endif -%}{% endif %}
{%- elif annotation.annotatedText %}
- {{calloutCharacter(annotation.color)}} {{annotation.annotatedText | nl2br}} [(p. {{annotation.pageLabel}})](zotero://open-pdf/library/items/{{annotation.attachment.itemKey}}?page={{annotation.pageLabel}}&annotation={{annotation.id}}) {% if annotation.hashTags %}{{annotation.hashTags}}{% endif %}
{%- endif -%}{%- endif -%}{%- endfor %}


{% endif %}
{% endpersist %}


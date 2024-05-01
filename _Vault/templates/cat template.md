---
aliases: ["{% if authors %}{% for author in authors %}{{author}}{%- endfor %}{% endif %} ({{date | format("YYYY")}}) {{title}}{{caseTitle}}"]
{%if shortTitle %}Title: "{{shortTitle}}"{%else%}Title: "{{title}}{{caseTitle}}"{% endif %}
{%- if bookTitle %}
BookTitle: "{{bookTitle}}" {%- endif %}{%if rights%}
Impression: {{rights}}{%endif%}
tags: zotero, literature-notes, reference
Type: {{itemType}}
---
# {% if authors %}{% for author in authors %}{{author}}{%- endfor %} {% endif %}({{date | format("YYYY")}}{{dateDecided}}) {{title}}{{caseTitle}}
## Abstract
{{abstractNote}}
> [!header]+
> > [!important]-
> > ```dataview
> > Table rows.important as ""
> > where file.name = this.file.name
> > group by tag
> 
> > [!metadata]-
> > [[Index]] 
> > {% if authors %}{% for author in authors %}{{author}}{%- endfor %} {% endif %}({{date | format("YYYY")}}{{dateDecided}}) {{title}}{{caseTitle}}
> > {% for c in creators %}{% if loop.first %}{{c.creatorType | capitalize}}s:: {% endif %}[[{{c.firstName|replace(".", "")}} {{c.lastName|replace(".", "")}}]]{% if not loop.last %}, {% endif %}{% endfor %} 
> > {% if itemType %}Item_Type:: [[{{itemType}}]]{%- endif %}
> > {% if bookTitle %}Book:: [[{{bookTitle}}]]{%- endif %} {% if proceedingsTitle %}
> > Proceedings_Title:: [[{{proceedingsTitle}}]]{%- endif %} {%- if caseName %}
> > Case_Name:: [[{{caseName}}]]{%- endif %}{%- if jurisdiction %}
> > Jurisdiction:: [[{{jurisdiction}}]]{%- endif %}{%- if court %}
> > Court:: [[{{Court}}]]{%- endif %} {%- if date %}
> > Year:: [[{{date | format("YYYY")}}]]{%- endif %}{%- if dateDecided %}
> > Year:: [[{{yearAsVolume}}]]{%- endif %}{%- if url %}
> > URL:: {{url}}{%- endif %}{%- if doi %}
> > DOI:: [[{{doi}}]]{%- endif %}{%- if citekey %}
> > Citekey:: {{citekey}}{%- endif %}{% if tags %}
> > Subjects:: {% for t in tags %}[[{{t.tag}}]]{% if not loop.last %}, {% endif %}{% endfor %} {% endif %}{%- if relations.length %}
> > Related:: {% for r in relations %} [[{{r.citekey}}]]{% if not loop.last %}, {% endif %} {% endfor %}{%- endif %}{% if editors %}
> > Editors:: {% for c in creators %}{% if c.creatorType=="editor" %}[[{{c.firstName|replace(".", "")}} {{c.lastName|replace(".", "")}}]]{% endif %}{% if not loop.last %}, {% endif %}{% endfor %}{% endif %} {% if translators %}
> > Translators:: [[{{translators|replace(".", "")}}]] {% endif %}{%- if rights %}
> > Verdict:: [[{{rights}}]] {%- endif %} {%- if attachments %}
> > Attachments: {%- for a in attachments | filterby("path", "endswith", ".pdf") %}
> > [{{a.title}}](file://{{a.path | replace(" ", "%20")}})  {%- endfor -%}.{%- endif %}
> 
> > [!reading]-
> > ```dataview
> > task from #todo/readinglist 
> > where file.name = this.file.name
> > ```
> > ```dataview
> > task from #researchprompt
> > where file.name = this.file.name
> > ```
## Annotations

{% for a in annotations %}{% if a.annotatedText %}{% if a.type == "underline" %}
{% if a.colorCategory == "Yellow" %}#example::[[Example]]<span class="example">"{{a.annotatedText}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.pageLabel}})
{% elif a.colorCategory == "Gray" %}### {{a.annotatedText}}{% elif a.colorCategory == "Blue" %}#### {{a.annotatedText}}{% elif a.colorCategory == "Cyan" %}#### {{a.annotatedText}}{% elif a.colorCategory == "Purple" %}##### {{a.annotatedText}}{% elif a.colorCategory == "Magenta" %}##### {{a.annotatedText}}{% elif a.colorCategory == "Orange" %}###### {{a.annotatedText}}{% else %}### {{a.annotatedText}}{% endif %}{% elif a.type == "strike" %}#### {{a.annotatedText}}{% elif a.color=="#434343" %}#### {{a.annotatedText}} {% elif a.tag=="h1" %}### {{a.annotatedText}} {% elif (a.color=="#767676") or (a.color=="#000000") %}##### {{a.annotatedText}} {% elif a.color=="#aaaaaa" %}### {{a.annotatedText}} {% elif (a.color=="#ffffff") or (a.colorCategory=="White") or (a.color=="#e56eee") -%}#### {{a.annotatedText}}{% elif (a.color=="#000000") or (a.colorCategory=="Black") -%}##### {{a.annotatedText}}
{% elif (a.color=="#37e5ff") or (a.color=="#38e5ff") or (a.color=="#2ea8e5") or (a.color=="#7fffff") or (a.colorCategory=="Cyan") %}#important:: [[Important]]  <span class="important">"{{a.annotatedText}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.pageLabel}})
{% elif (a.color=="#a33086") or (a.color=="#a32f86") or (a.color=="#a28ae5") or (a.color == "#bf7fbf") or (a.colorCategory=="Magenta") or (a.colorCategory=="Purple") %}#critique:: [[Critique]]  <span class="critique">"{{a.annotatedText}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.pageLabel}})
{% elif (a.color=="#ffc09e") %}- [ ] #therapy::[[Followup]]<span class="therapy">{{a.annotatedText}}</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.pageLabel}})
{% elif (a.color=="#fb88ff") or (a.color=="#ff809d") or (a.color=="#0000ff") or (a.color=="#ff7fff") or (a.colorCategory=="Pink") or (a.colorCategory=="Blue")%}#confusion:: [[Confusion]]  <span class="confusion">"{{a.annotatedText}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}})
{% elif (a.color=="#f19837") or (a.color=="#ff6f01") or (a.color=="#ffc09e") or (a.color=="#ffbf7f") or (a.color == "#ff7002") or (a.colorCategory=="Orange") %}#idea:: [[Idea]]  <span class="idea">"{{a.annotatedText}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.pageLabel}})
{% elif a.color=="#cccccc" or (a.color=="#aaaaaa") or (a.colorCategory=="Gray") %}#argument:: [[Argument]]  <span class="argument">"{{a.annotatedText}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.pageLabel}})
{% elif (a.color=="#fbf485") %}#example::[[Example]]<span class="example">"{{a.annotatedText}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.pageLabel}})
{% elif (a.color=="#ff6666") or (a.color=="#e52237") or (a.color=="#ff6666") or (a.color=="#e52136") or (a.color=="#ff7f7f") or (a.colorCategory=="Red") %}#disagreement:: [[Disagreement]]  <span class="disagreement">"{{a.annotatedText}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.pageLabel}})
{% elif (a.color=="#6ad928") or (a.color=="#5fb236") or (a.color=="#69d927") or (a.color=="#c5fb71") or (a.color=="#7fff7f") or (a.color=="#5fb236") or (a.colorCategory=="Green") %}- [ ] #todo/readinglist {{a.annotatedText}} [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}})
{% elif (a.color=="#ffff7f") or (a.color=="#ffd400") or (a.colorCategory=="Yellow") %}"{{a.annotatedText}}" [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}}) 
{% else %}"{{a.annotatedText}}" [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}})
{% endif %}{% endif %}
{%- if a.imageRelativePath %}![[{{a.imageRelativePath}}]]{%- endif %}
{% if a.comment %}
{% if (a.color=="#37e5ff") or (a.color=="#38e5ff") or (a.colorCategory=="Cyan") %}> [!important]+ 
> #important:: [[Important]] [[Cat]] <span class="important">"{{a.comment}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}})
{% elif (a.color=="#a33086") or (a.color=="#a32f86") or (a.color=="#a28ae5") or (a.color=="#a28ae5") or (a.colorCategory=="Purple") %}> [!critiques]+ Critique
> #critique:: [[Critique]] [[Cat]] <span class="critique">"{{a.comment}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}})
{% elif (a.color=="#e56eee") or (a.color=="#e56eee") or (a.color=="#fb88ff") or (a.color=="#ff809d") or (a.color=="#0000ff") or (a.colorCategory=="Magenta") or (a.colorCategory=="Blue")%}> [!confusion]+
> #confusion:: [[Confusion]] [[Cat]] <span class="confusion">"{{a.comment}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}})
{% elif (a.color=="#f19837") or (a.color=="#ff6f01") or (a.color=="#f19837") or (a.color=="#ffc09e") or (a.color == "#ff7002") or (a.colorCategory=="Orange") %}> [!ideas]+ Idea
> #idea:: [[Idea]] [[Cat]] <span class="idea">"{{a.comment}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}})
{% elif (a.color=="#cccccc") or (a.color=="#") or (a.colorCategory=="Gray") %}> [!arguments]+ Argument
> #argument:: [[Argument]] [[Cat]] <span class="argument">"{{a.comment}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}})
{% elif (a.color=="#ff6666") or (a.color=="#e52237") or (a.color=="#e52136") or (a.colorCategory=="Red") %}> [!disagreements]+ Disagreement
> #disagreement:: [[Disagreement]] [[Cat]] <span class="disagreement">"{{a.comment}}"</span> [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}})
{% elif (a.color=="#6ad928") or (a.color=="#5fb236") or (a.color=="#69d927") or (a.color=="#c5fb71") or (a.colorCategory=="Green") %}> [!reading]+ To Read
> - [ ] #todo/readinglist {{a.comment}} [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}})
{% else %}> [!comment]+
> [[Cat]]{{a.comment}} [p.{{a.pageLabel}}](zotero://open-pdf/library/items/{{a.attachment.itemKey}}?page={{a.page}})
{% endif %}{% endif %}{% endfor %}
{%- if markdownNotes %}
{{formattedAnnotations}}{{markdownNotes}}{%- endif -%}.
## Data
> [!footer]+
> 
> 
> > [!important]-
> > ```dataview
> > Table rows.important as ""
> > where file.name = this.file.name
> > group by tag
> > ```
> 
> 
> > [!ideas]-
> > ```dataview
> > Table rows.idea as ""
> > where file.name = this.file.name
> > group by tag
> > ```
> 
> 
> > [!disagreements]-
> > ```dataview
> > Table rows.disagreement as ""
> > where file.name = this.file.name
> > group by tag
> > ```
> 
> 
> > [!confusion]-
> > ```dataview
> > Table rows.confusion as ""
> > where file.name = this.file.name
> > group by tag
> > ```
> 
> 
> > [!critiques]-
> > ```dataview
> > Table rows.critique as ""
> > where file.name = this.file.name
> > group by tag
> > ```
> 
> 
> > [!arguments]-
> > ```dataview
> > Table rows.argument as ""
> > where file.name = this.file.name
> > group by tag
> > ```
> 
> 
> > [!reading]-
> >```tasks
> > not done
> > (description includes todo) OR (description includes researchprompt)
> > filename includes {{citekey}}
> > ```
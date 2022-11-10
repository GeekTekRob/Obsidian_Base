<%*
  let title = tp.file.title
  if (title.startsWith("Untitled")) {
    title = await tp.system.prompt("Title");
    await tp.file.rename(title);
  } 
  
  tR += "---"
%>

title:  <%* tR += title %>
created: "<% tp.file.creation_date() %>"
Aliases: 

---
**Last modified:** <%+ tp.file.last_modified_date() %>
**Tags:** #Code 

# <%* tR += title %>
---

### *SCRIPT*
```HTML

<CODE GOES HERE>

```


---

### *Notes*
- Note 01
- Note 02
- Note 03

### Reference
- Reference 01
- Reference 02
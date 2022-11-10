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
**Tags:** #


# <%* tR += title %>

---

### **SECTION 1**
---
Lorem Ipsum





### **SECTION 2**
___
Lorem Ipsum
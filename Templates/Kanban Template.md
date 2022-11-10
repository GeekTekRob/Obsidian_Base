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
kanban-plugin: basic

---
**Last modified:** <%+ tp.file.last_modified_date() %>
**Tags:** #Kanban

## To Do

- [ ] Example 1


## In Progress

- [ ] Example 2


## Done

**Complete**


## Removed

**Complete**




%% kanban:settings
```
{"kanban-plugin":"basic"}
```
%%
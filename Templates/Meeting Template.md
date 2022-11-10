<%*
  let title = tp.file.title
  if (title.startsWith("Untitled")) {
    title = await tp.system.prompt("Title");
    await tp.file.rename(title);
  } 
  
  tR += "---"
%>
title:  <%* tR += title %>
meetingdate: <% tp.date.now("YYYY-MM-DD HH:mm:ss") %>
attendees: {"Rob Hendrix"}
created: "<% tp.file.creation_date() %>"
Aliases: 

---
**Last modified:** <%+ tp.file.last_modified_date() %>
**Tags:** #Meeting

# <%* tR += title %>
#### **Meeting Date/Time:** `= this.meetingdate`
#### **Attendees:** `= this.attendees`
---

## GOALS / AGENDA
1. Item 1
2. Item 2

---

## NOTES
- Item 1
- Item 2

---

## ACTION ITEMS
- [ ] Task 1
- [ ] Task 2
- [ ] Task 3


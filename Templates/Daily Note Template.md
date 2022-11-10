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
**Tags:** #DailyNote

<< [[<%* tR += moment(title,'YYYY-MM-DD').subtract(1,"days").format("dddd, MMMM DD, YYYY") %>]] **|** [[<%* tR += moment(title,'YYYY-MM-DD').add(1,"days").format("dddd, MMMM DD, YYYY") %>]] >>

### This Week's Monday: [[<% tp.date.weekday("YYYY-MM-DD",1) %>]]

<%*

var quote;
var cite;

async function updateQuote() {
    // Fetch a random quote from the Quotable API
    //const response = await fetch("http://api.quotable.io/random?tags=famous-quotes,inspirational"); // example with tags
    const response = await fetch("http://api.quotable.io/random?tags=");
    const data = await response.json();
    if (response.ok) {
      // Update DOM elements
      quote = data.content;
      cite  = data.author;
    } else {
      quote = "An error occured";
      console.log(data);
    }
  }

await updateQuote();

tR += "> [!qotd]  ### **Today's Quote** \r\n";
tR += "> " + quote + "\r\n";
tR += "> - <cite>" + cite + "</cite>";

%>

### `fas:Tasks` To Do Today:
- [ ] Task 1
- [ ] Task 2
- [ ] Task 3



### `far:StickyNote` Notes: 
- Item 1
- Item 2
- Item 3



### `far:CalendarPlus` Individual Notes Created Today:
```dataview
List WHERE file.cday = date(<% moment(title,'YYYY-MM-DD').format("YYYY-MM-DD") %>) AND file.name != this.file.name SORT file.ctime desc
```


### `ris:CalendarTodo` Individual Notes Updated Today:
```dataview
List WHERE file.mday = date(<% moment(title,'YYYY-MM-DD').format("YYYY-MM-DD") %>) AND file.name != this.file.name SORT file.mtime desc
```





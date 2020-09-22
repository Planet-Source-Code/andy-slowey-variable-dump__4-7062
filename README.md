<div align="center">

## Variable Dump


</div>

### Description

Helps debugging by showing you what variables you may have set.
 
### More Info
 
No specific inputs!

I have typically used this with a debug variable and then used SERVER.EXECUTE("scriptname") to spit out all variables in a page. It saved me a bit of time debugging.

all variable collections, names and contents

None that I have found!


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Andy Slowey](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/andy-slowey.md)
**Level**          |Intermediate
**User Rating**    |3.8 (15 globes from 4 users)
**Compatibility**  |ASP \(Active Server Pages\)
**Category**       |[Debugging and Error Handling](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/debugging-and-error-handling__4-6.md)
**World**          |[ASP / VbScript](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/asp-vbscript.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/andy-slowey-variable-dump__4-7062/archive/master.zip)





### Source Code

```
<html>
<body>
<%
response.write("<H1>Core Dump</H1>")
response.write("<H2>Application</H2>")
For Each item in Application.Contents
If IsArray(item) Then
  for each i in item
   Response.write(item & " : " & Application.Contents(item) & "<BR>")
  Next
Else
  Response.write(item & " : " & Application.Contents(item) & "<BR>")
End If
next
response.write("<H2>Session</H2>")
For Each item in Session.Contents
If IsArray(item) Then
  for each i in item
   Response.write(item & " : " & Session.Contents(item) & "<BR>")
  Next
Else
  Response.write(item & " : " & Session.Contents(item) & "<BR>")
End If
next
response.write("<H2>Form</H2>")
For Each item in request.form
  If IsArray(item) Then
  for each i in item
   Response.write(item & " : " & Request.Form(item) & "<BR>")
  Next
Else
  Response.write(item & " : " & Request.Form(item) & "<BR>")
End If
next
response.write("<H2>QueryString</H2>")
For Each item in request.querystring
  If IsArray(item) Then
  for each i in item
   Response.write(item & " : " & Request.querystring(item) & "<BR>")
  Next
Else
  Response.write(item & " : " & Request.querystring(item) & "<BR>")
End If
next
%>
</body>
</html>
```


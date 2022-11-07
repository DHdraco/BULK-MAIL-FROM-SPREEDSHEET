# BULK-MAIL-FROM-SPREEDSHEET

This google app script will use the most recent draft in Gmail as a template.


# Features

* Handles duplicate entries (by email)
* Works on HTML and plain text emails


# Usage

1. Open google spreadsheet doc containing the data.  
2. Go to **`Tools -> Script editor`**
  1. Paste contents of **`bulkmail.gs`** there
  2. Save it
3. After saving script, you will notice a new menu **Bulk Mail** (At the top) in Spreadsheet.
4. From Spreadsheet, Go to **`Bulk Mail -> Send mail`**


## Example Spreadsheet
#sheet1

Email | Name | SendOrNot 
---------- | ----------|-------------
abc@gmail.com | Dhanush | SENT_ALREADY  
xyz@gmail.com |Bharadwaj |   

> here you can add as many fields as you want.  
#sheet2

subject | link1 | link2 
---------- | ----------|-------------
xyz | https://... | (https://...)     

> here just one field is enough to send **'bulkMails'** as you want.  

## Template

```
To: Email (here, put the title of email column)  
Subject: SOmething common to everyone.
Body:
Hi {{name}} some content will be entered
........................................
...........
     {{link1}}
     ..........
     {{link2}} 
 regards
 abc,
 cdef
<Body>
```  

> For every field you added in spreadsheet you have to add the same title name in “ {{ }} “  

## Mail sent to everyone

```
To: abc@def.com
Subject : Common subject
Body:
Hello Abc Xyz
PQR
<Body>
```

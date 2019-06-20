---
description: Aamgpt ist eine javascript-Funktion, die die Audience Manager-Cookie-Daten liest und diese Informationen an Google Publisher Tags sendet.
seo-description: Aamgpt ist eine javascript-Funktion, die die Audience Manager-Cookie-Daten liest und diese Informationen an Google Publisher Tags sendet.
seo-title: Audience Manager-Code für Google Publisher Tags
solution: Audience Manager
title: Audience Manager-Code für Google Publisher Tags
uuid: 24 ff 5 d 16-b 360-46 cc-a 4 c 6-6 db 34 d 7 fda 75
translation-type: tm+mt
source-git-commit: 6169e8aefc4c215c83d6229be7378f90453f19e9

---


# Audience Manager-Code für Google Publisher Tags {#audience-manager-code-for-google-publisher-tags}

`AamGpt` ist eine [!DNL JavaScript] Funktion, die die Audience Manager-Cookie-Daten liest und diese Informationen sendet [!DNL Google Publisher Tags].

>[!NOTE]
>
>Diese Funktion ist nicht erforderlich, wenn Sie über Ihren eigenen Code verfügen, um Audience Manager-Cookie-Daten aus den [!UICONTROL UUID] Cookies und Zielcookies zu lesen.

## Beispielcode

Platzieren Sie den `AamGpt` Code am oberen Rand der Seite, idealerweise im `<head>` Codeblock. Der `AamGpt` Code ist unten verfügbar:

```js
var AamGpt = {  
 strictEncode: function(str){ 
  return encodeURIComponent(str).replace(/[!'()]/g, escape).replace(/\*/g, "%2A"); 
 }, 
 getCookie: function(c_name) 
 { 
  var i,x,y,c=document.cookie.split(";"); 
  for (i=0;i<c.length;i++) 
  { 
   x=c[i].substr(0,c[i].indexOf("=")); 
   y=c[i].substr(c[i].indexOf("=")+1); 
   x=x.replace(/^\s+|\s+$/g,""); 
   if (x==c_name) 
   { 
    return unescape(y); 
   } 
  } 
 }, 
 getKey: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[0] != "undefined" && cList[0].match(/\w+/)) 
   { 
    return cList[0]; 
   } 
  }  
 }, 
 getValues: function(c_name){ 
  var c=this.getCookie(c_name); 
  c=this.strictEncode(c); 
  if(typeof c != "undefined" && c.match(/\w+%3D\w+/)){ 
   var cList=c.split("%3D"); 
   if(typeof cList[1] != "undefined" && cList[1].match(/\w+/)) 
   { 
    var vList=cList[1].split("%2C"); 
    if(typeof vList[0] != "undefined") 
    { 
     return vList; 
    } else { 
     return null; 
    }    
   } else { 
    return null; 
   } 
  } else { 
   return null; 
  } 
 } 
};
```

---
description: Code, der von DART Enterprise (und anderen Zieltypen) benötigt wird, um den UUID-Wert (Unique User ID) des Audience Managers zu erfassen.
seo-description: Code, der von DART Enterprise (und anderen Zieltypen) benötigt wird, um den UUID-Wert (Unique User ID) des Audience Managers zu erfassen.
seo-title: get_aamCookie-Code
solution: Audience Manager
title: get_aamCookie-Code
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 9%

---


# `get_aamCookie` Code {#get-aamcookie-code}

Code, der für [!DNL DART Enterprise] (und andere Zieltypen) erforderlich ist, um den Audience Manager-ID-Wert ([!DNL UUID]) zu erfassen.

Definieren Sie diese Funktion oben auf der Seite, idealerweise innerhalb des `<head>`-Codeblocks.

<!-- r_aam_de_cookie.xml -->

```js
<script type="text/javascript">
function get_aamCookie (c_name)
{
var i,x,y,ARRcookies=document.cookie.split(";");
for (i=0;i<ARRcookies.length;i++)
   {
   x=ARRcookies[i].substr(0,ARRcookies[i].indexOf("="));
   y=ARRcookies[i].substr(ARRcookies[i].indexOf("=")+1);
   x=x.replace(/^\s+|\s+$/g,"");
   if (x==c_name)
      { 
      return unescape(y);
      }
   }
}
</script>
```

---
description: Code, der von DART Enterprise (und anderen Zieltypen) benötigt wird, um den UUID-Wert (Unique User ID) des Audience Managers zu erfassen.
seo-description: Code required by DART Enterprise (and other destination types) to capture the Audience Manager unique user ID (UUID) value.
seo-title: get_aamCookie Code
solution: Audience Manager
title: get_aamCookie-Code
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
feature: Destination Basics
exl-id: 66e61a4b-908e-4950-8953-37a9920b67b5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 0%

---

# `get_aamCookie` {#get-aamcookie-code}

Für [!DNL DART Enterprise] (und andere Zieltypen) erforderlicher Code, um den Wert der eindeutigen Audience Manager-ID (Unique User ID, [!DNL UUID]) zu erfassen.

Definieren Sie diese Funktion oben auf der Seite, idealerweise innerhalb des `<head>`-Code-Blocks.

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

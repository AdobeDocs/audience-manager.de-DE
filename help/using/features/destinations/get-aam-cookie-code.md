---
description: Code, der von DART Enterprise (und anderen Zieltypen) benötigt wird, um den Wert für die Unique User ID (UUID) von Audience Manager zu erfassen.
seo-description: Code, der von DART Enterprise (und anderen Zieltypen) benötigt wird, um den Wert für die Unique User ID (UUID) von Audience Manager zu erfassen.
seo-title: get_aamCookie-Code
solution: Audience Manager
title: get_aamCookie-Code
uuid: 89c30fe3-dbe6-4d18-b161-104167d75bcd
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` Code {#get-aamcookie-code}

Code, der für [!DNL DART Enterprise] (und andere Zieltypen) erforderlich ist, um den Wert für die eindeutige Benutzer-ID ([!DNL UUID]) von Audience Manager zu erfassen.

Definieren Sie diese Funktion oben auf der Seite, idealerweise innerhalb des `<head>` Codeblocks.

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

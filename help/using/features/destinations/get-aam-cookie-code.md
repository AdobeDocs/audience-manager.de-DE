---
description: Der von DART Enterprise (und anderen Zieltypen) erforderliche Code, um den eindeutigen Benutzer-ID-Wert (UUID) des Audience Manager zu erfassen.
seo-description: Der von DART Enterprise (und anderen Zieltypen) erforderliche Code, um den eindeutigen Benutzer-ID-Wert (UUID) des Audience Manager zu erfassen.
seo-title: get_ aamcookie-Code
solution: Audience Manager
title: get_ aamcookie-Code
uuid: 89 c 30 fe 3-dbe 6-4 d 18-b 161-104167 d 75 bcd
translation-type: tm+mt
source-git-commit: abb66d75a0d47f5257ea8c63bdb59e604db801d3

---


# `get_aamCookie` Code {#get-aamcookie-code}

Code, der für [!DNL DART Enterprise] (und andere Zieltypen) erforderlich ist, um den eindeutigen Benutzer-ID ([!DNL UUID])-Wert des Audience Manager zu erfassen.

Definieren Sie diese Funktion am oberen Rand der Seite idealerweise im `<head>` Codeblock.

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

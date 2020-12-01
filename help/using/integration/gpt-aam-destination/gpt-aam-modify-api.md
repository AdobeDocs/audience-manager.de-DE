---
description: hinzufügen Sie eine if-Anweisung, um vor dem Aufruf der Google Publisher Tag .setTargeting-Methode nach Audience Manager-Cookies zu suchen.
seo-description: hinzufügen Sie eine if-Anweisung, um vor dem Aufruf der Google Publisher Tag .setTargeting-Methode nach Audience Manager-Cookies zu suchen.
seo-title: Ändern des GPT-API-Aufrufs setTargeting
solution: Audience Manager
title: Ändern des GPT-API-Aufrufs setTargeting
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 9%

---


# Ändern Sie den GPT `setTargeting`-API-Aufruf {#modify-the-gpt-settargeting-api-call}

hinzufügen Sie eine if-Anweisung, um vor dem Aufruf der [!DNL Google Publisher Tag] `.setTargeting`-Methode nach Audience Manager-Cookies zu suchen.

## Suchen Sie nach Audience Manager-Cookies mit einer `IF`-Anweisung

Die `.setTargeting`-Methode ruft Daten aus dem Audience Manager-Zielcookie und dem eindeutigen Benutzer-ID-Cookie ( `aam_uuid`) ab. Wenn `.setTargeting` jedoch aufgerufen wird, bevor [!UICONTROL DIL] diese Cookies schreibt oder die Cookies leer sind, werden beim Laden der Seite möglicherweise Fehler angezeigt. Um dies zu vermeiden, schließen Sie die `.setTargeting`-Methode in eine `if`-Anweisung ein, die nach diesen Cookies sucht. Wenn sie nicht eingestellt sind, verhindert diese Anweisung, dass `.setTargeting` die Funktion `AamGpt` aufruft.

### `IF` Beispiel für Anweisungscode

In diesem Beispiel lautet der Audience Manager-Ziel-Cookie-Name `Sample`. Sie legen diesen Namen fest, wenn Sie das Ziel-Cookie in der Benutzeroberfläche von Audience Manager erstellen. [!UICONTROL DIL] legt das  `aam_uuid` Cookie fest und der Name kann nicht geändert werden.

```js
if(typeof AamGpt.getCookie("Sample") != "undefined"){ 
  googletag.pubads().setTargeting(AamGpt.getKey("Sample"),AamGpt.getValues("Sample")); 
}; 
if(typeof AamGpt.getCookie("aam_uuid") != "undefined" ){ 
   googletag.pubads().setTargeting("aamId", AamGpt.getCookie("aam_uuid")); 
};
```

>[!IMPORTANT]
>
>Abhängig davon, wie Sie mit [!DNL Google Ad Manager] integrieren möchten, benötigen Sie nur einige der Zeilen im obigen Codebeispiel:
>
>* Clientseitige Integration: nur Zeilen 1-3 verwenden.
>* Serverseitige Integration: Keine der Zeilen wird benötigt.
>* Erfassen Sie die Protokolldateien für Berichte in [!DNL Google Ad Manager]: nur die Zeilen 4-6 verwenden. [!DNL Audience Manager] Mit diesem Code wird der Wert des `aam_uuid`-Cookies in die Protokolle eingefügt, damit sie zum Berichte aufgenommen werden können.


### `AamGpt` Funktionen und Datentypen

Definiert die Schlüsselvariablen, die in der `if`-Anweisung verwendet werden.

<table id="table_881391C9BDDF4FACAFC37A47B14B31A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funktion </th> 
   <th colname="col2" class="entry"> Typ </th> 
   <th colname="col3" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getKey </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Gibt den Schlüssel im Schlüssel-Wert-Segment-Paar zurück. Wenn Ihr Schlüssel-Wert-Paar beispielsweise aus <code> color=blue </code> bestand, wird <code> color </code> zurückgegeben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolgen-Array </p> </td> 
   <td colname="col3"> <p>Gibt Werte in einem Array zurück, z. B. <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Gibt die Audience Manager-Benutzer-ID zurück, z. B. <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Erstellen eines GPT-Ziels](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Audience Manager-Code für Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)


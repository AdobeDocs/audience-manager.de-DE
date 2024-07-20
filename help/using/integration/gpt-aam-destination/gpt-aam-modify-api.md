---
description: Fügen Sie eine if -Anweisung hinzu, um vor dem Aufruf der Google Publisher Tag .setTargeting -Methode nach Audience Manager-Cookies zu suchen.
seo-description: Add an if statement to check for Audience Manager cookies before calling the Google Publisher Tag .setTargeting method.
seo-title: Modify the GPT setTargeting API Call
solution: Audience Manager
title: Ändern des GPT-setTargeting-API-Aufrufs
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
feature: Third-party Integration
exl-id: cc34b7e8-7bbd-463f-9378-9d3a40c49594
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 5%

---

# Ändern des GPT `setTargeting`-API-Aufrufs {#modify-the-gpt-settargeting-api-call}

Fügen Sie eine if -Anweisung hinzu, um vor dem Aufruf der [!DNL Google Publisher Tag] `.setTargeting` -Methode nach Audience Manager-Cookies zu suchen.

## Überprüfen auf Audience Manager-Cookies mit einer `IF`-Anweisung

Die `.setTargeting` -Methode ruft Daten aus dem Audience Manager-Ziel-Cookie und dem Unique User-ID-Cookie ( `aam_uuid`) ab. Wenn jedoch `.setTargeting` aufgerufen wird, bevor [!UICONTROL DIL] diese Cookies schreibt oder die Cookies leer sind, können beim Laden der Seite Fehler auftreten. Um dies zu vermeiden, schließen Sie die `.setTargeting` -Methode in eine `if` -Anweisung ein, die nach diesen Cookies sucht. Wenn sie nicht festgelegt sind, verhindert diese Anweisung, dass `.setTargeting` die Funktion `AamGpt` aufruft.

### Beispiel für `IF` Statement-Code

In diesem Beispiel lautet der Audience Manager-Ziel-Cookie-Name `Sample`. Sie legen diesen Namen fest, wenn Sie das Ziel-Cookie in der Audience Manager-Benutzeroberfläche erstellen. [!UICONTROL DIL] setzt das `aam_uuid` -Cookie und der Name kann nicht geändert werden.

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
>Je nachdem, wie Sie die Integration mit [!DNL Google Ad Manager] durchführen möchten, benötigen Sie nur einige der Zeilen im obigen Codebeispiel:
>
>* Clientseitige Integration: nur die Zeilen 1 bis 3 verwenden.
>* Serverseitige Integration: Keine der Zeilen ist erforderlich.
>* Aufnahme von [!DNL Google Ad Manager] Protokolldateien für die Berichterstellung in [!DNL Audience Manager]: Verwenden Sie nur die Zeilen 4-6. Dieser Code fügt den Wert des `aam_uuid` -Cookies in die Protokolle ein, damit sie für die Berichterstellung erfasst werden können.

### `AamGpt` Funktionen und Datentypen

Definiert die in der `if` -Anweisung verwendeten Schlüsselvariablen.

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

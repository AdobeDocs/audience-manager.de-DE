---
description: Fügen Sie eine if-Anweisung hinzu, um auf Audience Manager-Cookies zu prüfen, bevor Sie die setTargeting-Methode für das Google Publisher-Tag aufrufen.
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

# Ändern des GPT-`setTargeting`-API-Aufrufs {#modify-the-gpt-settargeting-api-call}

Fügen Sie eine if-Anweisung hinzu, um auf Audience Manager-Cookies zu prüfen, bevor Sie die [!DNL Google Publisher Tag] `.setTargeting` aufrufen.

## Suchen nach Audience Manager-Cookies mit einer `IF`

Die `.setTargeting`-Methode ruft Daten aus dem Audience Manager-Ziel-Cookie und dem Unique-User-ID-Cookie ( `aam_uuid`) ab. Wenn `.setTargeting` jedoch aufgerufen wird, bevor [!UICONTROL DIL] diese Cookies schreibt, oder die Cookies leer sind, können Fehler beim Laden der Seite auftreten. Um dies zu vermeiden, schließen Sie die `.setTargeting`-Methode in eine `if`-Anweisung ein, die nach diesen Cookies sucht. Wenn sie nicht festgelegt sind, verhindert diese Anweisung, dass `.setTargeting` die Funktion `AamGpt` aufrufen.

### Code-Beispiel für `IF` Anweisung

In diesem Beispiel ist der Name des Ziel-Cookies des Audience Managers `Sample`. Sie legen diesen Namen fest, wenn Sie das Ziel-Cookie in der Benutzeroberfläche des Audience Managers erstellen. [!UICONTROL DIL] setzt das `aam_uuid` Cookie und der Name kann nicht geändert werden.

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
>Je nachdem, wie Sie mit [!DNL Google Ad Manager] integrieren möchten, benötigen Sie nur einige der Zeilen im obigen Code-Beispiel:
>
>* Client-seitige Integration: Verwenden Sie nur die Zeilen 1-3.
>* Server-seitige Integration: Keine der Zeilen ist erforderlich.
>* Nehmen Sie [!DNL Google Ad Manager] Protokolldateien für das Reporting in [!DNL Audience Manager] auf: Verwenden Sie nur die Zeilen 4-6. Dieser Code fügt den Wert des `aam_uuid`-Cookies in die Protokolle ein, damit sie zum Reporting aufgenommen werden können.

### `AamGpt` Funktionen und Datentypen

Definiert die in der `if`-Anweisung verwendeten Schlüsselvariablen.

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
   <td colname="col3"> <p>Gibt den Schlüssel im Schlüssel-Wert-Segmentpaar zurück. Wenn Ihr Schlüssel-Wert-Paar beispielsweise aus <code> color=blue </code> bestand, gibt dies <code> color </code> zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getValues </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolgen-Array </p> </td> 
   <td colname="col3"> <p>Gibt Werte in einem Array zurück, z. B. <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> AamGpt.getCookie </code> </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Gibt die Audience Manager-Benutzer-ID zurück, z. B. <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Erstellen eines GPT-Ziels](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Audience Manager-Code für Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

---
description: Fügen Sie eine if-Anweisung hinzu, um nach Audience Manager-Cookies zu suchen, bevor Sie die Google Publisher Tag.setTargeting-Methode aufrufen.
seo-description: Fügen Sie eine if-Anweisung hinzu, um nach Audience Manager-Cookies zu suchen, bevor Sie die Google Publisher Tag.setTargeting-Methode aufrufen.
seo-title: Ändern des GPT-setTargeting-API-Aufrufs
solution: Audience Manager
title: Ändern des GPT-setTargeting-API-Aufrufs
uuid: 0cd38f30-5d29-4511-a779-d32587f1dafb
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Ändern des GPT- `setTargeting` API-Aufrufs {#modify-the-gpt-settargeting-api-call}

Fügen Sie eine if-Anweisung hinzu, um vor dem Aufruf der [!DNL Google Publisher Tag] `.setTargeting` Methode nach Audience Manager-Cookies zu suchen.

## Cookies in Audience Manager mit einer `IF` Anweisung suchen

Die `.setTargeting` Methode ruft Daten aus dem Zielcookie von Audience Manager und dem eindeutigen Benutzer-ID-Cookie ( `aam_uuid`) ab. Wenn `.setTargeting` diese Cookies jedoch vor dem [!UICONTROL DIL] Schreiben aufgerufen werden oder die Cookies leer sind, werden beim Laden der Seite möglicherweise Fehler angezeigt. Um dies zu vermeiden, schließen Sie die `.setTargeting` Methode in eine `if` Anweisung ein, die nach diesen Cookies sucht. Wenn sie nicht eingestellt sind, verhindert diese Anweisung `.setTargeting` den Aufruf der `AamGpt` Funktion.

### `IF` Beispiel für Anweisungscode

In diesem Beispiel lautet der Name des Zielcookies in Audience Manager `Sample`. Sie legen diesen Namen fest, wenn Sie das Ziel-Cookie in der Benutzeroberfläche von Audience Manager erstellen. [!UICONTROL DIL] setzt das `aam_uuid` Cookie und der Name kann nicht geändert werden.

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
>Je nachdem, wie Sie mit [!DNL DFP]integrieren möchten, benötigen Sie nur einige der Zeilen im obigen Codebeispiel:
>
>* Clientseitige Integration: nur Zeilen 1-3 verwenden.
>* Serverseitige Integration: Keine der Zeilen wird benötigt.
>* Protokolldateien [!DNL DFP] zur Berichterstellung in [!DNL Audience Manager]: nur die Zeilen 4-6 verwenden. Mit diesem Code wird der Wert des `aam_uuid` Cookies in die Protokolle eingefügt, damit sie für die Berichterstellung eingebunden werden können.


### `AamGpt` Funktionen und Datentypen

Definiert die in der `if` Anweisung verwendeten Schlüsselvariablen.

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
   <td colname="col3"> <p>Gibt den Schlüssel im Schlüssel-Wert-Segment-Paar zurück. Wenn Ihr Schlüssel-Wert-Paar beispielsweise aus <code> color=blue </code>besteht, wird dies zurückgegeben <code> color </code>. </p> </td> 
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
>* [GPT-Ziel erstellen](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Audience Manager-Code für Google Publisher-Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)


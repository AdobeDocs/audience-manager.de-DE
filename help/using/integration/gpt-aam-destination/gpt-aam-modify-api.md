---
description: Fügen Sie eine if-Anweisung hinzu, um vor dem Aufruf der Google Publisher Tag. settargeting-Methode nach Audience Manager-Cookies zu suchen.
seo-description: Fügen Sie eine if-Anweisung hinzu, um vor dem Aufruf der Google Publisher Tag. settargeting-Methode nach Audience Manager-Cookies zu suchen.
seo-title: Ändern des GPT settargeting-API-Aufrufs
solution: Audience Manager
title: Ändern des GPT settargeting-API-Aufrufs
uuid: 0 cd 38 f 30-5 d 29-4511-a 779-d 32587 f 1 dafb
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Den GPT `setTargeting` -API-Aufruf ändern {#modify-the-gpt-settargeting-api-call}

Fügen Sie eine if-Anweisung hinzu, um vor dem Aufruf der [!DNL Google Publisher Tag]`.setTargeting` Methode nach Audience Manager-Cookies zu suchen.

## Überprüfen von Audience Manager-Cookies mit `IF` einer Anweisung

Die `.setTargeting` Methode ruft Daten aus dem Zielcookie von Audience Manager und dem eindeutigen Benutzer-ID-Cookie ( `aam_uuid`) ab. Wenn `.setTargeting` jedoch vor [!UICONTROL DIL] der Anzeige dieser Cookies aufgerufen wird oder die Cookies leer sind, werden möglicherweise Fehler angezeigt, wenn die Seite geladen wird. Um dies zu vermeiden, schließen Sie die `.setTargeting` Methode in eine `if` Anweisung ein, die nach diesen Cookies sucht. Wenn sie nicht festgelegt sind, verhindert `.setTargeting` diese Anweisung, dass die `AamGpt` Funktion aufgerufen wird.

### `IF` Muster-Codebeispiel

In diesem Beispiel lautet der Zielgruppenname des Zielgruppen-Managers `Sample`. Sie legen diesen Namen fest, wenn Sie das Zielcookie in der Benutzeroberfläche von Audience Manager erstellen. [!UICONTROL DIL] legt das `aam_uuid` Cookie fest und der Name kann nicht geändert werden.

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
>Je nachdem, wie [!DNL DFP]Sie integrieren möchten, benötigen Sie nur einige der Zeilen im obigen Codebeispiel:
>
>* Clientseitige Integration: nur Linien 1-3 verwenden.
>* Serverseitige Integration: keine der Zeilen erforderlich.
>* [!DNL DFP] Protokolldateien für die Berichterstellung in [!DNL Audience Manager]: nur Linien 4-6 verwenden. Dieser Code fügt den Wert des `aam_uuid` Cookies in die Protokolle ein, damit er für die Berichterstellung übernommen werden kann.


### `AamGpt` Funktionen und Datentypen

Definiert die Schlüsselvariablen, die in der `if` Anweisung verwendet werden.

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
   <td colname="col1"> <p> <code> Aamgpt. getkey </code> </p> </td> 
   <td colname="col2"> <p>Zeichenfolge </p> </td> 
   <td colname="col3"> <p>Gibt den Schlüssel im Schlüssel-Wert-Segment-Paar zurück. Wenn Ihr Schlüssel-Wert-Paar beispielsweise <code> aus color = blue </code>besteht, gibt dies <code> Farbe </code>zurück. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getvalues </code> </p> </td> 
   <td colname="col2"> <p>Array von Zeichenfolgen </p> </td> 
   <td colname="col3"> <p>Gibt Werte in einem Array zurück, z. B. <code> ["value 1", "value 2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getcookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Gibt die Benutzer-ID des Audience Manager zurück, z. <code></code>B. 12345. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Erstellen eines GPT-Ziels](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Audience Manager-Code für Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)


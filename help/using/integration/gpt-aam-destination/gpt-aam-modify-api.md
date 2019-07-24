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


# Modify the GPT `setTargeting` API Call {#modify-the-gpt-settargeting-api-call}

Add an if statement to check for Audience Manager cookies before calling the [!DNL Google Publisher Tag] `.setTargeting` method.

## Check for Audience Manager Cookies With an `IF` Statement

The `.setTargeting` method gets data from the Audience Manager destination cookie and the unique user ID cookie ( `aam_uuid`). However, if `.setTargeting` gets invoked before [!UICONTROL DIL] writes these cookies, or the cookies are empty, you may see errors when the page loads. To help avoid this, wrap the `.setTargeting` method in an `if` statement that checks for these cookies. If they're not set, this statement prevents `.setTargeting` from calling the `AamGpt` function.

### `IF` Muster-Codebeispiel

In this example, the Audience Manager destination cookie name is `Sample`. Sie legen diesen Namen fest, wenn Sie das Zielcookie in der Benutzeroberfläche von Audience Manager erstellen. [!UICONTROL DIL] legt das `aam_uuid` Cookie fest und der Name kann nicht geändert werden.

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
>Depending on how you want to integrate with [!DNL DFP], you only need some of the lines in the code sample above:
>
>* Clientseitige Integration: nur Linien 1-3 verwenden.
>* Serverseitige Integration: keine der Zeilen erforderlich.
>* [!DNL DFP] Protokolldateien für die Berichterstellung in [!DNL Audience Manager]: nur Linien 4-6 verwenden. This code inserts the value of the `aam_uuid` cookie into the logs so they can be ingested for reporting.


### `AamGpt` Funktionen und Datentypen

Defines the key variables used in the `if` statement.

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
   <td colname="col3"> <p>Gibt den Schlüssel im Schlüssel-Wert-Segment-Paar zurück. For example, if your key-value pair consisted of <code> color=blue </code>, this returns <code> color </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getvalues </code> </p> </td> 
   <td colname="col2"> <p>Array von Zeichenfolgen </p> </td> 
   <td colname="col3"> <p>Returns values in an array, e.g., <code> ["value1","value2"] </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Aamgpt. getcookie </code> </p> </td> 
   <td colname="col2"> <p>Int </p> </td> 
   <td colname="col3"> <p>Returns the Audience Manager user ID, e.g., <code> 12345 </code>. </p> </td> 
  </tr>
 </tbody>
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Erstellen eines GPT-Ziels](../../integration/gpt-aam-destination/gpt-aam-create-destination.md)
>* [Audience Manager-Code für Google Publisher Tags](../../integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)


---
description: In Destination Builder enthält der Abschnitt "Konfiguration"die Felder "Cookie-Domäne"und "Daten veröffentlichen in". Auf diese Weise können Sie Regeln erstellen, um festzustellen, ob ein Ziel ein Cookie setzt oder ein Cookie zurückgibt. Cookie-Domäne und Daten veröffentlichen, um unabhängig voneinander zu funktionieren, und sind optional. Sie können ein Cookie-Ziel erstellen, ohne eines davon zu verwenden.
seo-description: In Destination Builder enthält der Abschnitt "Konfiguration"die Felder "Cookie-Domäne"und "Daten veröffentlichen in". Auf diese Weise können Sie Regeln erstellen, um festzustellen, ob ein Ziel ein Cookie setzt oder ein Cookie zurückgibt. Cookie-Domäne und Daten veröffentlichen, um unabhängig voneinander zu funktionieren, und sind optional. Sie können ein Cookie-Ziel erstellen, ohne eines davon zu verwenden.
seo-title: Optionale Einstellungen für Cookie-Ziele
solution: Audience Manager
title: Optionale Einstellungen für Cookie-Ziele
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 7%

---


# Optionale Einstellungen für Cookie-Ziele {#optional-settings-cookies}

In [!UICONTROL Destination Builder] enthält [!UICONTROL Configuration section] die Felder [!UICONTROL Cookie Domain] und [!UICONTROL Publish Data To]. Auf diese Weise können Sie Regeln erstellen, um festzustellen, ob ein Ziel ein Cookie setzt oder ein Cookie zurückgibt. [!UICONTROL Cookie Domain] und  [!UICONTROL Publish Data To] arbeiten unabhängig voneinander und sind optional. Sie können ein Cookie-Ziel erstellen, ohne eines davon zu verwenden.

## Cookie-Domäne: Syntax und Beispiele {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cookie-Domäne </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Syntax</b> </p> </td> 
   <td colname="col2"> <p>Das Feld <span class="wintitle"> Cookie-Domäne</span> akzeptiert eine einfache Textzeichenfolge, mit der Sie Cookies in einer angegebenen Domäne oder in allen Domänen setzen können. Bei Verwendung dieser Funktion: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Legen Sie für jedes Cookie-Ziel nur eine Domäne fest. Geben Sie nicht mehrere Domänen in das Feld <span class="wintitle"> Cookie-Domäne</span> ein. Erstellen Sie stattdessen ein anderes <span class="wintitle">-Ziel</span>. </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Verwenden Sie keine Platzhalterzeichen. </li> 
     </ul> </p> <p> Lassen Sie das Feld <span class="wintitle"> Cookie-Domäne</span> leer, um ein Cookie für alle Domänen festzulegen. Dies ist die Standardeinstellung. </p> <p>So legen Sie Cookies für eine bestimmte Domäne und Subdomänen fest: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Geben Sie den Namen der Domäne in das Feld <span class="wintitle"> Cookie-Domäne</span> ein. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Beginn des Domänennamens mit einem Punkt. Beispiel, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">Das Präfix <code> https://www</code> ist nicht erforderlich. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Beispiel</b> </p> </td> 
   <td colname="col2"> <p>Ein einfaches Beispiel: Angenommen, wir haben eine fiktive Website namens sports.com. Sports.com hat Domains für Golf, Baseball und Fußball. Um ein Cookie in allen Sportdomänen einzurichten, geben Sie dieses in das Feld <span class="wintitle"> Cookie-Domäne</span> ein, wie unten dargestellt: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Dadurch wird <span class="keyword"> Audience Manager</span> angewiesen, ein Cookie in einer Domäne zu setzen, die das Muster <code><i>something</i></code>.sports.com enthält. Eine komplexere Beispielreihe finden Sie unten. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Beispiele für komplexe Cookie-Domänen

Diese Beispiele zeigen Ihnen, ob [!DNL Audience Manager] je nach Konfiguration der Option [!UICONTROL Cookie Domain] ein Cookie setzt.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Webseite </th> 
   <th colname="col2" class="entry">Cookie-Domäne: .sports.com <p>Cookie-Set </p> </th> 
   <th colname="col3" class="entry">Cookie-Domäne: .golf.sports.com <p>Cookie-Set </p> </th> 
   <th colname="col4" class="entry">Cookie-Domäne: Leer <p>Cookie-Set </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sports.com</b> </p> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Nein </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sports.com</b> </p> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Ja </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>baseball.sports.com</b> </p> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Nein </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sports.golf.com</b> </p> </td> 
   <td colname="col2"> Nein </td> 
   <td colname="col3"> Nein </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
 </tbody> 
</table>

## Daten für {#publish-data-to} veröffentlichen

Die [!UICONTROL Publish Data To]-Einstellungen geben ein Cookie zurück, wenn die Domäne die von den ausgewählten Optionen festgelegten Kriterien erfüllt. Zu den Optionen zählen:

* **[!UICONTROL All of our domains]**: (Standard) Gibt eine  [!DNL cookie] für jede Domäne zurück.
* **[!UICONTROL Only the selected domains]**: Gibt ein Cookie nur für die in der Liste &quot;Domänen&quot;ausgewählten Domänen zurück.
* **[!UICONTROL All of our domains except the selected domains]**: Verhindert, dass ausgewählte Domänen eine  [!DNL cookie]empfangen. Alle anderen Domänen können ein [!DNL cookie] empfangen.

>[!MORELIKETHIS]
>
>* [Cookie-Ziel erstellen](../../features/destinations/create-cookie-destination.md)
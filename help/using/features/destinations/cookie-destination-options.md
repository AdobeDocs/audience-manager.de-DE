---
description: Im Zielgenerator enthält der Abschnitt Konfiguration die Felder Cookie-Domäne und Publish-Daten an . Mit diesen Regeln können Sie Regeln erstellen, um zu bestimmen, ob ein Ziel ein Cookie setzt oder ein Cookie zurückgibt. Cookie-Domäne und Publish-Daten Damit arbeiten sie unabhängig voneinander und sind optional. Sie können ein Cookie-Ziel erstellen, ohne eines davon zu verwenden.
seo-description: In Destination Builder, the Configuration section contains the Cookie Domain and Publish Data To fields. These let you create rules to determine if a destination sets a cookie or returns a cookie. Cookie Domain and Publish Data To work independently of each other and are optional. You can create a cookie destination without using either of them.
seo-title: Optional Settings for Cookie Destinations
solution: Audience Manager
title: Optionale Einstellungen für Cookie-Ziele
feature: Destination Basics
exl-id: b44f386e-4d43-41c3-b8ce-88b83d5d83c2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 4%

---

# Optionale Einstellungen für Cookie-Ziele {#optional-settings-cookies}

In [!UICONTROL Destination Builder] enthält der [!UICONTROL Configuration section] die Felder [!UICONTROL Cookie Domain] und [!UICONTROL Publish Data To]. Mit diesen Regeln können Sie Regeln erstellen, um zu bestimmen, ob ein Ziel ein Cookie setzt oder ein Cookie zurückgibt. [!UICONTROL Cookie Domain] und [!UICONTROL Publish Data To] funktionieren unabhängig voneinander und sind optional. Sie können ein Cookie-Ziel erstellen, ohne eines davon zu verwenden.

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
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Legen Sie für jedes Cookie-Ziel nur eine Domäne fest. Geben Sie nicht mehrere Domänen in das Feld <span class="wintitle"> Cookie-Domäne</span> ein. Erstellen Sie stattdessen ein weiteres <span class="wintitle"> Ziel</span> . </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Verwenden Sie keine Platzhalterzeichen. </li> 
     </ul> </p> <p> Lassen Sie das Feld <span class="wintitle"> Cookie-Domäne</span> leer, um ein Cookie für alle Domänen festzulegen. Dies ist die Standardeinstellung. </p> <p>So legen Sie Cookies für eine bestimmte Domäne und Subdomänen fest: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Geben Sie den Namen der Domäne in das Feld <span class="wintitle"> Cookie-Domäne</span> ein. </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Starten Sie den Domänennamen mit einem Punkt. Beispiel: <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">Das Präfix <code> https://www</code> ist nicht erforderlich. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Beispiel</b> </p> </td> 
   <td colname="col2"> <p>Ein einfaches Beispiel: Angenommen, wir haben eine fiktive Site namens sports.com. Sports.com hat Domänen für Golf, Baseball und Fußball. Um ein Cookie in allen Sportdomänen festzulegen, geben Sie es wie unten gezeigt in das Feld <span class="wintitle"> Cookie-Domäne</span> ein: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Dadurch wird <span class="keyword"> Audience Manager</span> angewiesen, ein Cookie in einer Domäne zu setzen, die das Muster <code><i>something</i></code>.sports.com enthält. Eine komplexere Auswahl von Beispielen finden Sie unten. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Beispiele für komplexe Cookie-Domänen

Diese Beispiele zeigen Ihnen, ob [!DNL Audience Manager] basierend auf der Konfiguration der [!UICONTROL Cookie Domain] -Option ein Cookie setzt.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Webseite </th> 
   <th colname="col2" class="entry">Cookie-Domäne: .sports.com <p>Cookie-Satz </p> </th> 
   <th colname="col3" class="entry">Cookie-Domäne: .golf.sports.com <p>Cookie-Satz </p> </th> 
   <th colname="col4" class="entry">Cookie-Domäne: Leer <p>Cookie-Satz </p> </th> 
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
   <td colname="col1"> <p> <b>Golf.sports.com</b> </p> </td> 
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
   <td colname="col1"> <p> <b>sports.Golf.com</b> </p> </td> 
   <td colname="col2"> Nein </td> 
   <td colname="col3"> Nein </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
 </tbody> 
</table>

## Publish-Daten an {#publish-data-to}

Die Einstellungen für [!UICONTROL Publish Data To] geben ein Cookie zurück, wenn die Domäne die Kriterien erfüllt, die von den ausgewählten Optionen festgelegt wurden. Zu den Optionen zählen:

* **[!UICONTROL All of our domains]**: (Standard) Gibt für eine beliebige Domäne den Wert [!DNL cookie] zurück.
* **[!UICONTROL Only the selected domains]**: Gibt ein Cookie nur für die Domänen zurück, die in der Domänenliste ausgewählt sind.
* **[!UICONTROL All of our domains except the selected domains]**: Verhindert, dass ausgewählte Domänen eine [!DNL cookie] erhalten. Alle anderen Domänen können einen [!DNL cookie] erhalten.

>[!MORELIKETHIS]
>
>* [Erstellen eines Cookie-Ziels](../../features/destinations/create-cookie-destination.md)

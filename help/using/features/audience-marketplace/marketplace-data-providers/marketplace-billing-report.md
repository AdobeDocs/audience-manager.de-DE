---
description: Erstellen Sie einen Audience Marketplace-Abrechnungsbericht, um die Daten-Feed-Nutzung für den Vormonat für jede Abonnentin und jeden Abonnenten anzuzeigen. Sie können jederzeit einen Bericht für den Vormonat erstellen. Der Bericht ist jedoch genauer, wenn Sie ihn am oder nach dem 10. Tag des aktuellen Monats erstellen.
seo-description: Generate an Audience Marketplace billing report to view data feed usage for the previous month for each of your subscribers. You can create a report for the previous month at any time. However, the report is more accurate when you generate it on or after the 10th day of the current month.
seo-title: Billing for Data Feed Providers
solution: Audience Manager
title: Abrechnung für Daten-Feed-Anbieter
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
exl-id: aca2cec1-d3a0-421c-83ca-1c11e9e7d4c7
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 1%

---

# Abrechnung für Daten-Feed-Anbieter {#billing-for-data-feed-providers}

Erstellen Sie einen [!DNL Audience Marketplace] Abrechnungsbericht, um die Daten-Feed-Nutzung für den Vormonat für jede Abonnentin und jeden Abonnenten anzuzeigen. Sie können jederzeit einen Bericht für den Vormonat erstellen. Der Bericht ist jedoch genauer, wenn Sie ihn am oder nach dem 10. Tag des aktuellen Monats erstellen.

## Rechnungsbericht herunterladen {#download-billing-report}

Herunterladen eines Berichts:

1. Gehe zu **[!UICONTROL Audience Marketplace > Receivables]**.
1. Klicken Sie auf **[!UICONTROL Generate Billing Report]**.

## Definierte Berichtsfelder {#report-fields-defined}

Ein Abrechnungsbericht enthält die folgenden Informationen.

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Berichtsfeld </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Datenanbieter-PID</span></b> </p> </td> 
   <td colname="col2"> <p>Ihr <span class="keyword"> Audience Manager </span> Datenanbieter-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Name <b><span class="uicontrol"> Datenanbieters</span></b> </p> </td> 
   <td colname="col2"> <p>Name Ihres Unternehmens oder Ihrer Organisation. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Käufer-PID</span></b> </p> </td> 
   <td colname="col2"> <p>Käufer-ID (Abonnenten-ID) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Name des Käufers</span></b> </p> </td> 
   <td colname="col2"> <p>Der Unternehmens- oder Organisationsname des Käufers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Feed-ID</span></b> </p> </td> 
   <td colname="col2"> <p>Die ID des Daten-Feeds </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Feed-Name</span></b> </p> </td> 
   <td colname="col2"> <p>Der Name des Daten-Feeds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Anwendungsfälle für Pläne</span></b> </p> </td> 
   <td colname="col2"> <p>Mithilfe von Anwendungsfällen können Verkäufer steuern, wie Käufer Daten verwenden. Zu den Optionen zählen: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segmente und Überschneidungen </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modellierung </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Aktivierung </li> 
    </ul> <p>Siehe <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> von Plantypen für Daten-Feeds</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Maßeinheit</span></b> </p> </td> 
   <td colname="col2"> <p>Zeigt CPM oder Flatfee-Abrechnung an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Listenpreis</span></b> </p> </td> 
   <td colname="col2"> <p>Die Abonnementgebühr für jeden Daten-Feed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Rabattpreis</span></b> </p> </td> 
   <td colname="col2"> <p>Die Abonnementgebühr für einen ermäßigten Daten-Feed. Siehe <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> für Datenanbieter</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Einheiten</span></b> </p> </td> 
   <td colname="col2"> <p>Variiert je nach Feed-Preistyp: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Flatfee-Daten-Feeds: Gibt nur 1 zurück. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM-Daten-Feeds: Gibt die tatsächliche Nutzung für CPM-Daten-Feeds zurück. Wenn ein Abonnent keine Impressionsdaten für einen CPM-Feed bereitgestellt hat, ist die Zelle Units leer und die Zelle Flag wird auf 1 gesetzt. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Gesamtkosten</span></b> </p> </td> 
   <td colname="col2"> <p>Der Betrag <span class="keyword"> Audience Managers </span> der einem Käufer in Rechnung gestellt wird. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Abrechnungszeitraum</span></b> </p> </td> 
   <td colname="col2"> <p> Im Bericht ist dies der letzte Tag des Vormonats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Eingabedatum</span></b> </p> </td> 
   <td colname="col2"> <p>Das Datum, an dem ein Käufer Abonnement-/Nutzungsinformationen eingegeben hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Startdatum des Abonnements</span></b> </p> </td> 
   <td colname="col2"> <p>Das Datum, an dem ein Käufer sein Daten-Feed-Abonnement begonnen hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Enddatum des Abonnements</span></b> </p> </td> 
   <td colname="col2"> <p>Das Datum, an dem ein Käufer sein Daten-Feed-Abonnement beendet hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Flag</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Nur für CPM-Feeds</i>. Zu den Flag-Optionen gehören: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Zeigt an, dass ein Abonnent Nutzungsinformationen an <span class="keyword"> Audience Manager gemeldet hat</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Zeigt an, dass ein Abonnent keine Nutzungsinformationen an <span class="keyword"> Audience Manager gemeldet hat</span>. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Abrechnung und Impression-Zuordnung für CPM-Daten-Feeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Abrechnungs- und Impressionszuweisung für Flatfee-Daten-Feeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [So melden Sie die Nutzung von CPM](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

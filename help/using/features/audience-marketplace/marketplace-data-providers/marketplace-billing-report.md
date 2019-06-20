---
description: Erstellen Sie einen Audience Marketplace-Rechnungsbericht, um die Datenfeed-Nutzung für den vorherigen Monat für jeden Ihrer Abonnenten anzuzeigen. Sie können jederzeit einen Bericht für den vorherigen Monat erstellen. Der Bericht ist jedoch genauer, wenn Sie ihn am oder nach dem 10. Tag des aktuellen Monats generieren.
seo-description: Erstellen Sie einen Audience Marketplace-Rechnungsbericht, um die Datenfeed-Nutzung für den vorherigen Monat für jeden Ihrer Abonnenten anzuzeigen. Sie können jederzeit einen Bericht für den vorherigen Monat erstellen. Der Bericht ist jedoch genauer, wenn Sie ihn am oder nach dem 10. Tag des aktuellen Monats generieren.
seo-title: Rechnungsstellung für Datenfeed-Anbieter
solution: Audience Manager
title: Rechnungsstellung für Datenfeed-Anbieter
topic: DIL-API
uuid: 4 e 11 dbd 2-91 fd -4 b 59-a 66 d -86 a 92 e 0 de 655
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Rechnungsstellung für Datenfeed-Anbieter {#billing-for-data-feed-providers}

Erstellen Sie einen [!DNL Audience Marketplace] Rechnungsbericht, um die Datenfeed-Nutzung für den vorherigen Monat für jeden Ihrer Abonnenten anzuzeigen. Sie können jederzeit einen Bericht für den vorherigen Monat erstellen. Der Bericht ist jedoch genauer, wenn Sie ihn am oder nach dem 10. Tag des aktuellen Monats generieren.

## Einen Rechnungsbericht herunterladen {#download-billing-report}

So laden Sie einen Bericht herunter

1. Gehe **[!UICONTROL Audience Marketplace > Receivables]** zu.
1. Klicken Sie auf **[!UICONTROL Generate Billing Report]**.

## Berichtsfelder definiert {#report-fields-defined}

Ein Rechnungsbericht enthält die folgenden Informationen.

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Berichtfeld </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Datenanbieter-PID</span></b> </p> </td> 
   <td colname="col2"> <p>Ihre <span class="keyword"> Audience Manager</span> -Datenanbieter-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Datenanbieter-Name</span></b> </p> </td> 
   <td colname="col2"> <p>Ihr Unternehmens- oder Firmenname. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Käufer-PID</span></b> </p> </td> 
   <td colname="col2"> <p>Käufer (Abonnenten)-ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Name des Käufers</span></b> </p> </td> 
   <td colname="col2"> <p>Der Name des Unternehmens oder Unternehmens des Käufers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Feed-ID</span></b> </p> </td> 
   <td colname="col2"> <p>Die ID des Datenfeeds </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Feed-Name</span></b> </p> </td> 
   <td colname="col2"> <p>Der Name des Datenfeeds. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Anwendungsfälle planen</span></b> </p> </td> 
   <td colname="col2"> <p>Mithilfe von Anwendungsfällen können Verkäufer steuern, wie Käufer Daten verwenden. Zu den Optionen zählen: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segmente und Überlappung </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modellierung </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Activation </li> 
    </ul> <p>Siehe <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Planen von Typen für Datenfeeds</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Maßeinheit</span></b> </p> </td> 
   <td colname="col2"> <p>Gibt die CPM- oder einfache Zahlungsabrechnung an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Listenpreis</span></b> </p> </td> 
   <td colname="col2"> <p>Die Abonnementgebühr für jeden Datenfeed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Preisreduzierter Preis</span></b> </p> </td> 
   <td colname="col2"> <p>Abonnementgebühr für einen disgezählten Datenfeed. Siehe <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Rabatte für Datenanbieter</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Einheiten</span></b> </p> </td> 
   <td colname="col2"> <p>Variiert je nach Feed-Preistyp: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Einfache Gebühr für Datenfeeds: Gibt nur 1 zurück. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM-Datenfeeds: Gibt den tatsächlichen Nutzungsbetrag für CPM-Datenfeeds zurück. Wenn ein Abonnent keine Impressionsdaten für einen CPM-Feed bereitgestellt hat, ist die Zelle "Einheiten" leer und die Zelle" Flag" ist auf 1 gesetzt. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Gesamtkosten</span></b> </p> </td> 
   <td colname="col2"> <p>Der Betrag, den <span class="keyword"> Audience Manager</span> einen Käufer angibt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Rechnungsstellungszeitraum</span></b> </p> </td> 
   <td colname="col2"> <p> Im Bericht ist dies der letzte Tag des vorherigen Monats. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Entrydatum</span></b> </p> </td> 
   <td colname="col2"> <p>Das Datum, an dem ein Käufer Abonnement-/Nutzungsinformationen eingegeben hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Abonnementstartdatum</span></b> </p> </td> 
   <td colname="col2"> <p>Das Datum, an dem ein Käufer das Datenfeed-Abonnement gestartet hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Abonnementenddatum</span></b> </p> </td> 
   <td colname="col2"> <p>Das Datum, an dem ein Käufer ihr Datenfeed-Abonnement beendet hat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Flag</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Nur für CPM-Feeds</i>. Zu den Flag-Optionen zählen: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Gibt an, dass ein Abonnent die Nutzungsinformationen an <span class="keyword"> Audience Manager gemeldet</span>hat. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Gibt an, dass ein Abonnent die Nutzungsinformationen an <span class="keyword"> Audience Manager nicht gemeldet</span>hat. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORE_ LIKE_ THIS]
>
>* [Rechnungsstellung und Impressionszuordnung für CPM-Datenfeeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Rechnungsstellung und Impression-Zuordnung für einfache gebührenpflichtige Datenfeeds](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [So melden Sie CPM-Nutzung](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)


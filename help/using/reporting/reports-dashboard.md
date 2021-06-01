---
description: Verwenden Sie das Dashboard, um Informationen über die Unique Visitor-Zählungen Ihrer Partner anzuzeigen, aufgeschlüsselt nach Eigenschaftstypen und Segmenten für einen bestimmten Zeitraum.
seo-description: Verwenden Sie das Dashboard, um Informationen über die Unique Visitor-Zählungen Ihrer Partner anzuzeigen, aufgeschlüsselt nach Eigenschaftstypen und Segmenten für einen bestimmten Zeitraum.
seo-title: Berichte-Dashboard
solution: Audience Manager
title: Berichte-Dashboard
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Berichtsreferenz
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 1%

---

# Berichte-Dashboard {#reports-dashboard}

Verwenden Sie das Dashboard, um Informationen zu den Unique Visitor-Zählungen für einen bestimmten Zeitraum nach Eigenschaftstypen und Segmenten aufgeschlüsselt anzuzeigen.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] verwendet  [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]), um Benutzergruppenberechtigungen auf  [!UICONTROL Dashboard]zu erweitern. Benutzer können nur Informationen im Dashboard sehen, die sie anzeigen können. [!UICONTROL RBAC] -Funktion können Sie steuern, welche Berichtsdaten interne Teams anzeigen können.

Eine Agentur, die verschiedene Advertiser-Konten verwaltet, kann beispielsweise Benutzergruppenberechtigungen so konfigurieren, dass ein Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht sehen kann. Dieses Dashboard kann zur Fehlerbehebung bei Problemen mit der Datenbereitstellung verwendet werden.

Wenn Sie z. B. einen Rückgang oder eine Spitze bei den Unique Users insgesamt feststellen, bei denen die Aufschlüsselung des Typs des Unique Users erfolgt (regelbasiert im Vergleich zu integriert), haben Sie einen besseren Ausgangspunkt, um ein potenzielles Datenbereitstellungsproblem nachzuverfolgen. Wenn Sie einen Rückgang bei den Unique Users insgesamt und bei integrierten Unique Users feststellen, können Sie zum Bericht [!UICONTROL On-boarding Status] gehen, um zu sehen, ob ein Problem mit einer eingehenden Datei aufgetreten ist.

**So greifen Sie auf das Dashboard zu:**

1. Klicken Sie im oberen Navigationsmenü auf **[!UICONTROL Dashboard]**.
2. ** Optional: Wählen Sie aus der Dropdownliste den gewünschten Zeitraum aus dem letzten Berichtsdatum aus (7 Tage, 14 Tage (Standard), 30 Tage oder 60 Tage).

   Je nach ausgewähltem Zeitraum zeigt die Deltaänderung in den Bedienfeldern [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] und [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] die Änderung der Unique Visitors in der Zielgruppe im Zeitraum, der heute endet, im Vergleich zum vorherigen Zeitraum derselben Länge an. Wenn Sie beispielsweise &quot;7 Tage&quot;auswählen, vergleicht der Delta die Unique Visitors über die letzten sieben Tage, die heute enden, mit den Unique Visitors für die sieben Tage, die vor sieben Tagen endeten.

   >[!NOTE]
   >
   >Sie können eine ungewöhnliche Delta-Änderung untersuchen, indem Sie einen [!UICONTROL Trend] -Bericht ausführen. Wenn Sie beispielsweise in den letzten sieben Tagen eine ungewöhnlich große Delta-Änderung feststellen, können Sie einen [!UICONTROL Trend] -Bericht für die letzten 14 Tage (2 x 7) ausführen, um die Zahlen besser zu verstehen.

   Je nach den Berechtigungen des angemeldeten Benutzers werden die folgenden Bereiche angezeigt:

   * [Partner Uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Größte Eigenschaften/am meisten geänderte Eigenschaften](../reporting/reports-dashboard.md#largest-traits)
   * [Größte Segmente/am meisten geänderte Segmente](../reporting/reports-dashboard.md#most-changed-segments)

3. ** OptionalKlicken Sie  **[!UICONTROL Normalize]** über einem beliebigen Diagramm, um alle Daten auf derselben Skala anzuzeigen. Sie können auch mit dem Mauszeiger über einen Datenpunkt fahren, um weitere Informationen anzuzeigen.

## Partner Uniques {#partner-uniques}

Berechtigung erforderlich für Anzeige: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

In diesem Bereich wird die Anzahl der Unique Visitors im angegebenen Zeitraum angezeigt. Einzelne farbcodierte Zeilen stellen die Gesamtanzahl der Unique Visitors und die Anzahl der Unique Visitors dar, die anhand algorithmischer, regelbasierter und integrierter Eigenschaften erfasst wurden.

>[!NOTE]
>
>Die Gesamtanzahl der Unique Visitors stellt Besucher dar, die über regelbasierte oder integrierte Eigenschaften erfasst werden. Die Gesamtanzahl der Unique Visitors entspricht jedoch nicht der Summe der Unique Visitors, die mit den regelbasierten und integrierten Eigenschaften erfasst wurden. Derselbe Unique User kann in einem dieser beiden Eigenschaftstypen dargestellt werden.

## Größte Eigenschaften/am meisten geänderte Eigenschaften {#largest-traits}

Berechtigung erforderlich für Anzeige: [!UICONTROL View Traits].

![](assets/largest_traits.png)

In diesem Bereich wird die Anzahl der Unique Visitors angezeigt, die von verschiedenen Eigenschaften erfasst werden.

Verwenden Sie die Dropdownliste **[!UICONTROL Show]**, um Informationen über verschiedene Eigenschaftstypen anzuzeigen: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded] oder [!UICONTROL Rule-Based].

Dieses Bedienfeld enthält die folgenden Registerkarten:

<table id="table_DA48BDEB4E0143BEA4EB85AC26FF6AE3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tab </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Größte Eigenschaften</span> </p> </td> 
   <td colname="col2"> <p>Zeigt Informationen über die Anzahl der Unique Visitors, sortiert nach Anzahl (von höchster zu niedrigster), sowie die Deltamaänderung der Unique Visitors im angegebenen Zeitraum an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Am häufigsten geänderte Eigenschaften</span> </p> </td> 
   <td colname="col2"> <p>Zeigt Informationen über die Anzahl der Unique Visitors, sortiert nach der Delta-Änderung. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Größte Segmente/am meisten geänderte Segmente {#most-changed-segments}

Berechtigung erforderlich für Anzeige: [!UICONTROL View Segments].

![](assets/largest_segments.png)

In diesem Bedienfeld wird die Anzahl der Unique Visitors angezeigt, die von verschiedenen Segmenten in Echtzeit erfasst werden.

Dieses Bedienfeld enthält die folgenden Registerkarten:

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Registerkarte </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Größte Segmente</span> </p> </td> 
   <td colname="col2"> <p>Zeigt Informationen über die Anzahl der Unique Visitors und die Delta-Änderung der Unique Visitors während des angegebenen Zeitraums an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Am häufigsten geänderte Segmente</span> </p> </td> 
   <td colname="col2"> <p>Zeigt Informationen über die Anzahl der Unique Visitors, sortiert nach der Delta-Änderung. </p> </td> 
  </tr> 
 </tbody> 
</table>

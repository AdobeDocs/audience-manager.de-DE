---
description: Verwenden Sie das Dashboard, um Informationen über die Unique Visitor-Zahlen Ihrer Partner anzuzeigen, aufgeschlüsselt nach Eigenschaftstypen und Segmenten für einen bestimmten Zeitraum.
seo-description: Use the Dashboard to view information about your partners' unique visitor counts broken down by trait types and segments for a specified time frame.
seo-title: Reports Dashboard
solution: Audience Manager
title: Berichte-Dashboard
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
feature: Reporting Reference
exl-id: 1ca0280a-d67b-46f7-9c58-effc5be4e38f
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 0%

---

# Berichte-Dashboard {#reports-dashboard}

Verwenden Sie das Dashboard, um Informationen über die Anzahl Ihrer Unique Visitors anzuzeigen, aufgeschlüsselt nach Eigenschaftstypen und Segmenten für einen bestimmten Zeitrahmen.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] verwendet [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]), um Benutzergruppenberechtigungen auf die [!UICONTROL Dashboard] zu erweitern. Benutzer können nur Informationen im Dashboard sehen, für die sie über die Berechtigung zum Anzeigen verfügen. Mit [!UICONTROL RBAC] Funktion können Sie steuern, welche Berichtsdaten interne Teams anzeigen können.

Beispielsweise kann eine Agentur, die verschiedene Advertiser-Konten verwaltet, Benutzergruppenberechtigungen so konfigurieren, dass ein Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht sehen kann. Dieses Dashboard kann zur Fehlerbehebung bei Problemen mit der Datenbereitstellung verwendet werden.

Wenn Sie beispielsweise einen Rückgang oder eine Spitze bei der Gesamtzahl eindeutiger Benutzer mit der Aufschlüsselung des Typs eindeutiger Benutzer (regelbasiert vs. integriert) bemerken, haben Sie einen besseren Ausgangspunkt, um ein potenzielles Problem bei der Datenbereitstellung zu ermitteln. Wenn Sie einen Rückgang bei der Gesamtzahl der eindeutigen Benutzer und der integrierten eindeutigen Benutzer feststellen, können Sie den [!UICONTROL On-boarding Status]-Bericht aufrufen, um zu sehen, ob ein Problem mit einer eingehenden Datei aufgetreten ist.

**So greifen Sie auf das Dashboard zu:**

1. Klicken Sie im oberen Navigationsmenü auf **[!UICONTROL Dashboard]**.
2. *Optional* Wählen Sie den gewünschten Zeitrahmen aus dem letzten Berichtsdatum aus der Dropdown-Liste (7 Tage, 14 Tage (Standard), 30 Tage oder 60 Tage).

   Je nach ausgewähltem Zeitraum zeigt die Delta-Änderung in den Bedienfeldern [!UICONTROL Largest Traits] > [!UICONTROL Most Changed Traits] und [!UICONTROL Largest Segments] > [!UICONTROL Most Changed Segments] die Änderung der Unique Visitors in der Zielgruppe in dem Zeitraum an, der heute endet, verglichen mit dem vorherigen Zeitraum derselben Länge. Wenn Sie beispielsweise 7 Tage auswählen, vergleicht das Delta die Unique Visitors der letzten sieben Tage, die heute enden, mit den Unique Visitors der sieben Tage, die vor sieben Tagen enden.

   >[!NOTE]
   >
   >Sie können eine Delta-Änderung, die ungewöhnlich erscheint, untersuchen, indem Sie einen [!UICONTROL Trend] Bericht ausführen. Wenn Sie beispielsweise in den letzten sieben Tagen eine ungewöhnlich große Delta-Änderung feststellen, können Sie einen [!UICONTROL Trend] für die letzten 14 Tage (2 x 7) ausführen, um die Zahlen besser zu verstehen.

   Je nach den Berechtigungen des angemeldeten Benutzers werden die folgenden Bedienfelder angezeigt:

   * [Eindeutige Partner](../reporting/reports-dashboard.md#partner-uniques)
   * [Größte Eigenschaften/Am häufigsten geänderte Eigenschaften](../reporting/reports-dashboard.md#largest-traits)
   * [Größte Segmente/Am häufigsten geänderte Segmente](../reporting/reports-dashboard.md#most-changed-segments)

3. *Optional* Klicken Sie auf **[!UICONTROL Normalize]** über einem Diagramm, um alle Daten auf derselben Skala anzuzeigen. Sie können auch den Mauszeiger über einen beliebigen Datenpunkt bewegen, um weitere Informationen anzuzeigen.

## Eindeutige Partner {#partner-uniques}

Berechtigung erforderlich zum Anzeigen: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

In diesem Bedienfeld wird die Anzahl der Unique Visitors im angegebenen Zeitraum angezeigt. Einzelne, farbcodierte Zeilen stellen die Gesamtzahl der Unique Visitors und die Anzahl der Unique Visitors dar, die mithilfe algorithmischer, regelbasierter und integrierter Eigenschaften erfasst wurden.

>[!NOTE]
>
>Die Gesamtzahl der Unique Visitors stellt Besuchende dar, die über regelbasierte oder integrierte Eigenschaften erfasst wurden. Die Gesamtzahl der Unique Visitors entspricht jedoch nicht der Summe der Unique Visitors, die mithilfe der regelbasierten und integrierten Eigenschaften erfasst wurden. Derselbe eindeutige Benutzer kann in einem dieser beiden Eigenschaftstypen dargestellt werden.

## Größte Eigenschaften/Am häufigsten geänderte Eigenschaften {#largest-traits}

Berechtigung erforderlich zum Anzeigen: [!UICONTROL View Traits].

![](assets/largest_traits.png)

In diesem Bedienfeld wird die Anzahl der Unique Visitors angezeigt, die von verschiedenen Eigenschaften erfasst wurden.

Verwenden Sie die Dropdown-Liste **[!UICONTROL Show]** , um Informationen zu verschiedenen Typen von Eigenschaften anzuzeigen: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded] oder [!UICONTROL Rule-Based].

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
   <td colname="col1"> <p><span class="wintitle"> größten Eigenschaften</span> </p> </td> 
   <td colname="col2"> <p>Zeigt Informationen zur Anzahl der Unique Visitors an, sortiert nach Anzahl (vom höchsten zum niedrigsten Wert), und listet auch die Delta-Änderung der Unique Visitors während des angegebenen Zeitraums auf. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> die meisten geänderten Eigenschaften</span> </p> </td> 
   <td colname="col2"> <p>Zeigt Informationen über die Anzahl der Unique Visitors an, sortiert nach der Delta-Änderung. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Größte Segmente/Am häufigsten geänderte Segmente {#most-changed-segments}

Berechtigung erforderlich zum Anzeigen: [!UICONTROL View Segments].

![](assets/largest_segments.png)

In diesem Bedienfeld wird die Anzahl der Unique Visitors angezeigt, die von verschiedenen Segmenten in Echtzeit erfasst wurden.

Dieses Bedienfeld enthält die folgenden Registerkarten:

<table id="table_8E22E0579FA74C5A86CC40B40B2548BE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tab </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> größten Segmente</span> </p> </td> 
   <td colname="col2"> <p>Zeigt Informationen über die Anzahl der Unique Visitors und die Delta-Änderung von Unique Visitors im angegebenen Zeitraum an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> am häufigsten geänderten Segmente</span> </p> </td> 
   <td colname="col2"> <p>Zeigt Informationen über die Anzahl der Unique Visitors an, sortiert nach der Delta-Änderung. </p> </td> 
  </tr> 
 </tbody> 
</table>

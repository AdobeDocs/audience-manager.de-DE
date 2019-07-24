---
description: Mit dem Dashboard können Sie Informationen über die Anzahl der individuellen Besucher Ihrer Partner anzeigen, aufgeschlüsselt nach Eigenschaften und Segmenten für einen bestimmten Zeitraum.
seo-description: Mit dem Dashboard können Sie Informationen über die Anzahl der individuellen Besucher Ihrer Partner anzeigen, aufgeschlüsselt nach Eigenschaften und Segmenten für einen bestimmten Zeitraum.
seo-title: Dashboard für Berichte
solution: Audience Manager
title: Dashboard für Berichte
uuid: 350 eee 2 d -72 f 7-42 a 7-916 b -60 f 9 a 362 c 5 cf
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Reports Dashboard {#reports-dashboard}

Verwenden Sie das Dashboard, um Informationen zu Ihren individuellen Besucherzählungen nach Eigenschaften und Segmenten für einen bestimmten Zeitraum anzuzeigen.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] verwendet ( [!UICONTROL Role Based Access Control][!UICONTROL RBAC]) zum Erweitern von Benutzergruppenberechtigungen auf [!UICONTROL Dashboard]. Benutzer können nur Informationen über das Dashboard anzeigen, die sie zur Ansicht berechtigt haben. [!UICONTROL RBAC] können Sie steuern, welche Berichtsdaten interne Teams anzeigen können.

Beispielsweise kann eine Agentur, die verschiedene Advertiserkonten verwaltet, Berechtigungen für Benutzergruppen konfigurieren, damit ein Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht anzeigen kann. Dieses Dashboard kann zur Fehlerbehebung bei Problemen mit der Datenauslieferung verwendet werden.

Wenn Sie z. B. einen Tiefpunkt oder eine Spitze in den einzelnen Unique Users mit der Aufschlüsselung des individuellen Benutzers (regelbasiert und direkt aufsteigend) bemerken, haben Sie einen besseren Ausgangspunkt, um ein potenzielles Problem bei der Datenauslieferung zu verfolgen. If you notice a dip in total unique users and in on-boarded unique users, you can go to the [!UICONTROL On-boarding Status] report to see if there was an issue with an inbound file.

**So greifen Sie auf das Dashboard zu:**

1. In the top navigation menu, click **[!UICONTROL Dashboard]**.
2. *Optional* wählen Sie den gewünschten Zeitraum aus dem letzten Berichtsdatum aus der Dropdownliste (7 Tage, 14 Tage (Standardeinstellung), 30 Tage oder 60 Tage).

   Depending on the period selected, the delta change in the [!UICONTROL Largest Traits] &gt; [!UICONTROL Most Changed Traits] and [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] panels displays the change in unique visitors in the audience over the period ending today vs. the prior period of the same length. Wenn Sie z. B. 7 Tage auswählen, vergleicht das Delta die individuellen Besucher in den letzten sieben Tagen, die am aktuellen Tag enden, mit den individuellen Besuchern der sieben Tage, die vor sieben Tagen enden.

   >[!NOTE]
   >
   >You can investigate a delta change that seems out of the ordinary by running a [!UICONTROL Trend] report. For example, if you see an unusually large delta change during the last seven days, you could run a [!UICONTROL Trend] report for the last 14 days (2 x 7) to better understand the numbers.

   Je nach den Berechtigungen des angemeldeten Benutzers werden die folgenden Bereiche angezeigt:

   * [Partner Uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Größte Eigenschaften/Am meisten geänderte Eigenschaften](../reporting/reports-dashboard.md#largest-traits)
   * [Größte Segmente/am meisten geänderte Segmente](../reporting/reports-dashboard.md#most-changed-segments)

3. *Optionaler* Klicken **[!UICONTROL Normalize]** über jedem Diagramm, um alle Daten in derselben Skala anzuzeigen. Sie können auch den Mauszeiger über einen Datenpunkt bewegen, um weitere Informationen anzuzeigen.

## Partner Uniques {#partner-uniques}

Permission Required to View: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Dieses Bedienfeld zeigt die Anzahl individueller Besucher während des angegebenen Zeitraums an. Einzelne, farbkodierte Linien stellen die Gesamtanzahl individueller Besucher und die Anzahl der Unique Visitors dar, die mithilfe von algorithmischen, regelbasierten und onboardierten Eigenschaften erfasst wurden.

>[!NOTE]
>
>Die Gesamtanzahl individueller Besucher stellt Besucher dar, die über regelbasierte oder in Bord befindliche Eigenschaften erfasst wurden. Die Gesamtanzahl individueller Besucher entspricht jedoch nicht der Summe der Unique Visitors, die mithilfe der regelbasierten und onboardierten Eigenschaften erfasst wurden. Derselbe Unique User kann in beiden beiden Eigenschaften dargestellt werden.

## Largest Traits/Most Changed Traits {#largest-traits}

Permission Required to View: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Dieses Bedienfeld zeigt die Anzahl der individuellen Besucher an, die von verschiedenen Eigenschaften erfasst wurden.

Use the **[!UICONTROL Show]** drop-down list to display information about different types of traits: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded], or [!UICONTROL Rule-Based].

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
   <td colname="col2"> <p>Zeigt Informationen über die Anzahl der individuellen Besucher an, die nach Anzahl sortiert sind (am niedrigsten zu den niedrigsten) und zeigt die Delta-Änderung individueller Besucher während des angegebenen Zeitraums an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Am meisten geänderte Eigenschaften</span> </p> </td> 
   <td colname="col2"> <p>Zeigt Informationen über die Anzahl der durch die Delta-Änderung sortierten Unique Visitors an. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Largest Segments/Most Changed Segments {#most-changed-segments}

Permission Required to View: [!UICONTROL View Segments].

![](assets/largest_segments.png)

Dieses Bedienfeld zeigt die Anzahl der individuellen Besucher an, die von verschiedenen Segmenten in Echtzeit erfasst wurden.

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
   <td colname="col1"> <p><span class="wintitle"> Größte Segmente</span> </p> </td> 
   <td colname="col2"> <p>Zeigt Informationen über die Anzahl individueller Besucher und die Delta-Änderung individueller Besucher während des angegebenen Zeitraums an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Am meisten geänderte Segmente</span> </p> </td> 
   <td colname="col2"> <p>Zeigt Informationen über die Anzahl der durch die Delta-Änderung sortierten Unique Visitors an. </p> </td> 
  </tr> 
 </tbody> 
</table>


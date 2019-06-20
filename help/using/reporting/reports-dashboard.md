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


# Dashboard für Berichte {#reports-dashboard}

Verwenden Sie das Dashboard, um Informationen zu Ihren individuellen Besucherzählungen nach Eigenschaften und Segmenten für einen bestimmten Zeitraum anzuzeigen.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] verwendet ( [!UICONTROL Role Based Access Control][!UICONTROL RBAC]) zum Erweitern von Benutzergruppenberechtigungen auf [!UICONTROL Dashboard]. Benutzer können nur Informationen über das Dashboard anzeigen, die sie zur Ansicht berechtigt haben. [!UICONTROL RBAC] können Sie steuern, welche Berichtsdaten interne Teams anzeigen können.

Beispielsweise kann eine Agentur, die verschiedene Advertiserkonten verwaltet, Berechtigungen für Benutzergruppen konfigurieren, damit ein Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht anzeigen kann. Dieses Dashboard kann zur Fehlerbehebung bei Problemen mit der Datenauslieferung verwendet werden.

Wenn Sie z. B. einen Tiefpunkt oder eine Spitze in den einzelnen Unique Users mit der Aufschlüsselung des individuellen Benutzers (regelbasiert und direkt aufsteigend) bemerken, haben Sie einen besseren Ausgangspunkt, um ein potenzielles Problem bei der Datenauslieferung zu verfolgen. Wenn Sie ein Dip in Unique Users und in Unique Users für Unique Users beachten, können Sie den [!UICONTROL On-boarding Status] Bericht aufrufen, um zu sehen, ob es ein Problem mit einer Inbound-Datei gibt.

**So greifen Sie auf das Dashboard zu:**

1. Klicken **[!UICONTROL Dashboard]** Sie im oberen Navigationsmenü auf.
2. *Optional* wählen Sie den gewünschten Zeitraum aus dem letzten Berichtsdatum aus der Dropdownliste (7 Tage, 14 Tage (Standardeinstellung), 30 Tage oder 60 Tage).

   Je nach ausgewähltem Zeitraum zeigt die Delta-Änderung in den Bereichen [!UICONTROL Largest Traits] &quot; &gt; [!UICONTROL Most Changed Traits] «und&quot; [!UICONTROL Largest Segments] &gt; [!UICONTROL Most Changed Segments] «die Änderung bei Unique Visitors in der Zielgruppe über den Zeitraum an, der heute endet und im vorherigen Zeitraum der gleichen Länge. Wenn Sie z. B. 7 Tage auswählen, vergleicht das Delta die individuellen Besucher in den letzten sieben Tagen, die am aktuellen Tag enden, mit den individuellen Besuchern der sieben Tage, die vor sieben Tagen enden.

   >[!NOTE]
   >
   >Sie können eine Delta-Änderung untersuchen, die durch Ausführen eines [!UICONTROL Trend] Berichts standardmäßig nicht normal angezeigt wird. Wenn Sie in den letzten sieben Tagen beispielsweise ungewöhnlich große Delta-Änderungen sehen, können Sie einen [!UICONTROL Trend] Bericht für die letzten 14 Tage (2 x 7) ausführen, um die Zahlen besser zu verstehen.

   Je nach den Berechtigungen des angemeldeten Benutzers werden die folgenden Bereiche angezeigt:

   * [Partner Uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Größte Eigenschaften/Am meisten geänderte Eigenschaften](../reporting/reports-dashboard.md#largest-traits)
   * [Größte Segmente/am meisten geänderte Segmente](../reporting/reports-dashboard.md#most-changed-segments)

3. *Optionaler* Klicken **[!UICONTROL Normalize]** über jedem Diagramm, um alle Daten in derselben Skala anzuzeigen. Sie können auch den Mauszeiger über einen Datenpunkt bewegen, um weitere Informationen anzuzeigen.

## Partner Uniques {#partner-uniques}

Zur Ansicht erforderliche Berechtigung: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Dieses Bedienfeld zeigt die Anzahl individueller Besucher während des angegebenen Zeitraums an. Einzelne, farbkodierte Linien stellen die Gesamtanzahl individueller Besucher und die Anzahl der Unique Visitors dar, die mithilfe von algorithmischen, regelbasierten und onboardierten Eigenschaften erfasst wurden.

>[!NOTE]
>
>Die Gesamtanzahl individueller Besucher stellt Besucher dar, die über regelbasierte oder in Bord befindliche Eigenschaften erfasst wurden. Die Gesamtanzahl individueller Besucher entspricht jedoch nicht der Summe der Unique Visitors, die mithilfe der regelbasierten und onboardierten Eigenschaften erfasst wurden. Derselbe Unique User kann in beiden beiden Eigenschaften dargestellt werden.

## Größte Eigenschaften/Am meisten geänderte Eigenschaften {#largest-traits}

Zur Ansicht erforderliche Berechtigung: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Dieses Bedienfeld zeigt die Anzahl der individuellen Besucher an, die von verschiedenen Eigenschaften erfasst wurden.

Verwenden Sie die **[!UICONTROL Show]** Dropdownliste, um Informationen zu verschiedenen Eigenschaften anzuzeigen: [!UICONTROL All Traits][!UICONTROL Algorithmic][!UICONTROL Onboarded], oder [!UICONTROL Rule-Based].

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

## Größte Segmente/am meisten geänderte Segmente {#most-changed-segments}

Zur Ansicht erforderliche Berechtigung: [!UICONTROL View Segments].

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


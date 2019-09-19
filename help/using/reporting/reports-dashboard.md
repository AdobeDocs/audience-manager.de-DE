---
description: Verwenden Sie das Dashboard, um Informationen zu den individuellen Besucherzahlen Ihrer Partner anzuzeigen, aufgeschlüsselt nach Eigenschaftentypen und Segmenten für einen bestimmten Zeitraum.
seo-description: Verwenden Sie das Dashboard, um Informationen zu den individuellen Besucherzahlen Ihrer Partner anzuzeigen, aufgeschlüsselt nach Eigenschaftentypen und Segmenten für einen bestimmten Zeitraum.
seo-title: Berichte-Dashboard
solution: Audience Manager
title: Berichte-Dashboard
uuid: 350eee2d-72f7-42a7-916b-60f9a362c5cf
translation-type: tm+mt
source-git-commit: ad4721cd2ff1f4b2b7cb814cbafdef1f59138a26

---


# Berichte-Dashboard {#reports-dashboard}

Verwenden Sie das Dashboard, um Informationen über die Zählung Ihrer individuellen Besucher für einen bestimmten Zeitraum nach Eigenschafts- und Segmenttypen aufzuschlüsseln.

<!-- 

c_dashboard.xml

 -->

[!DNL Audience Manager] verwendet [!UICONTROL Role Based Access Control] ([!UICONTROL RBAC]), um die Benutzergruppenberechtigungen auf die [!UICONTROL Dashboard]zu erweitern. Benutzer können nur Informationen im Dashboard anzeigen, die sie anzeigen dürfen. [!UICONTROL RBAC] -Funktion können Sie steuern, welche Berichtsdaten interne Teams anzeigen können.

Eine Agentur, die verschiedene Advertiser-Konten verwaltet, kann z. B. Benutzergruppenberechtigungen so konfigurieren, dass einem Team, das das Konto von Advertiser A verwaltet, die Berichtsdaten von Advertiser B nicht angezeigt werden. Dieses Dashboard kann zur Fehlerbehebung von Problemen bei der Datenbereitstellung verwendet werden.

Wenn Sie z. B. einen Tiefpunkt oder eine Spitze bei Unique Users mit der Unterteilung des Typs Unique User (regelbasiert im Vergleich zu eingebettet) feststellen, haben Sie einen besseren Ausgangspunkt, um ein potenzielles Datenbereitstellungsproblem zu verfolgen. Wenn Sie einen Tiefpunkt bei den Unique Users und bei den eingebetteten Unique Users feststellen, können Sie zum [!UICONTROL On-boarding Status] Bericht gehen, um zu sehen, ob ein Problem mit einer eingehenden Datei aufgetreten ist.

**So greifen Sie auf das Dashboard zu:**

1. Klicken Sie im oberen Navigationsmenü auf **[!UICONTROL Dashboard]**.
2. *Optional* Wählen Sie den gewünschten Zeitraum aus dem letzten Berichtsdatum aus der Dropdownliste (7 Tage, 14 Tage (Standard), 30 Tage oder 60 Tage).

   Je nach ausgewähltem Zeitraum zeigt die Delta-Änderung in den [!UICONTROL Largest Traits] &gt;- [!UICONTROL Most Changed Traits] und [!UICONTROL Largest Segments] &gt;- [!UICONTROL Most Changed Segments] Bedienfeldern die Veränderung der Unique Visitors in der Zielgruppe im Zeitraum an, der heute endet, im Vergleich zum vorherigen Zeitraum derselben Länge. Wenn Sie beispielsweise 7 Tage auswählen, vergleicht das Delta die individuellen Besucher der letzten sieben Tage mit den individuellen Besuchern der letzten sieben Tage.

   >[!NOTE]
   >
   >Sie können eine Delta-Änderung untersuchen, die ungewöhnlich erscheint, indem Sie einen [!UICONTROL Trend] Bericht ausführen. Wenn Sie z. B. in den letzten sieben Tagen eine ungewöhnlich große Delta-Änderung sehen, können Sie einen Bericht für die letzten 14 Tage (2 x 7) ausführen, um die Zahlen besser zu verstehen. [!UICONTROL Trend]

   Je nach den Berechtigungen des angemeldeten Benutzers werden die folgenden Bereiche angezeigt:

   * [Partner Uniques](../reporting/reports-dashboard.md#partner-uniques)
   * [Größte Eigenschaften/am meisten geänderte Eigenschaften](../reporting/reports-dashboard.md#largest-traits)
   * [Größte Segmente/Am meisten geänderte Segmente](../reporting/reports-dashboard.md#most-changed-segments)

3. *Optional* Klicken Sie auf **[!UICONTROL Normalize]** ein Diagramm, um alle Daten auf derselben Skala anzuzeigen. Sie können den Mauszeiger auch über einen Datenpunkt bewegen, um weitere Informationen anzuzeigen.

## Partner Uniques {#partner-uniques}

Berechtigung zum Anzeigen erforderlich: [!UICONTROL View All Traits].

![](assets/partner_uniques.png)

Dieser Bereich zeigt die Anzahl der individuellen Besucher während des angegebenen Zeitraums an. Einzelne farbkodierte Linien stellen die Gesamtanzahl der individuellen Besucher und die Anzahl der individuellen Besucher dar, die mit algorithmischen, regelbasierten und Bordmerkmalen erfasst werden.

>[!NOTE]
>
>Die Gesamtanzahl der Unique Visitors stellt Besucher dar, die über regelbasierte oder über Bordmerkmale erfasste Besucher erfasst wurden. Die Gesamtanzahl der individuellen Besucher entspricht jedoch nicht der Summe der individuellen Besucher, die mit den regelbasierten und integrierten Eigenschaften erfasst wurden. Derselbe eindeutige Benutzer kann in einem dieser beiden Eigenschaftstypen dargestellt werden.

## Größte Eigenschaften/am meisten geänderte Eigenschaften {#largest-traits}

Berechtigung zum Anzeigen erforderlich: [!UICONTROL View Traits].

![](assets/largest_traits.png)

Dieser Bereich zeigt die Anzahl der individuellen Besucher an, die von verschiedenen Eigenschaften erfasst wurden.

Verwenden Sie die **[!UICONTROL Show]** Dropdownliste, um Informationen zu verschiedenen Arten von Eigenschaften anzuzeigen: [!UICONTROL All Traits], [!UICONTROL Algorithmic], [!UICONTROL Onboarded]oder [!UICONTROL Rule-Based].

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
   <td colname="col2"> <p>Zeigt Informationen über die Anzahl der individuellen Besucher sortiert nach Anzahl (am höchsten bis am niedrigsten) und listet die Delta-Veränderung individueller Besucher während des angegebenen Zeitraums auf. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Am meisten geänderte Eigenschaften</span> </p> </td> 
   <td colname="col2"> <p>Zeigt Informationen zur Anzahl der individuellen Besucher sortiert nach der Delta-Änderung an. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Größte Segmente/Am meisten geänderte Segmente {#most-changed-segments}

Berechtigung zum Anzeigen erforderlich: [!UICONTROL View Segments].

![](assets/largest_segments.png)

In diesem Bedienfeld wird die Anzahl der individuellen Besucher angezeigt, die von verschiedenen Segmenten in Echtzeit erfasst werden.

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
   <td colname="col2"> <p>Zeigt Informationen zur Anzahl der individuellen Besucher und zur Delta-Änderung individueller Besucher während des angegebenen Zeitraums an. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Am häufigsten geänderte Segmente</span> </p> </td> 
   <td colname="col2"> <p>Zeigt Informationen zur Anzahl der individuellen Besucher sortiert nach der Delta-Änderung an. </p> </td> 
  </tr> 
 </tbody> 
</table>


---
description: In diesem Artikel wird beschrieben, wie Zielgruppen von Audience Manager und Adobe Experience Platform gemeinsam genutzt werden.
seo-description: In diesem Artikel wird beschrieben, wie Zielgruppen von Audience Manager und Adobe Experience Platform gemeinsam genutzt werden.
seo-title: Freigabe von Zielgruppen zwischen Audience Manager und Adobe Experience Platform
solution: Audience Manager
title: Freigabe von Zielgruppen zwischen Audience Manager und Adobe Experience Platform
keywords: Freigabe von AEP-Zielgruppen, AEP-Segmente, Platform-Segmente, Segmentfreigabe, Zielgruppenfreigabe, Segmente freigeben
feature: Plattformintegration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: 6900b56b4e0258ed0c4ddf94ef7b1f2c7e48a50d
workflow-type: tm+mt
source-wordcount: '1480'
ht-degree: 2%

---

# Freigabe von Experience Platform-Segmenten mit Audience Manager- und anderen Experience Cloud-Lösungen {#aam-aep-audience-sharing}

>[!NOTE]
>
> Wenden Sie sich an Ihren Adobe-Vertriebsmitarbeiter, um den Zugriff auf diese Funktion zu entsperren.

## Überblick {#overview}

Die Freigabe von Zielgruppen zwischen Audience Manager und Adobe Experience Platform ermöglicht es Ihnen, Ihre Audience Manager-Eigenschaften und -Segmente für Adobe Experience Platform und umgekehrt freizugeben. Sie benötigen [[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html), um die Zielgruppenfreigabe zwischen Audience Manager und Adobe Experience Platform zu aktivieren.

Sie können Audience Manager-Eigenschaften und -Segmente in Experience Platform verwenden, um Ihren Kundenprofilen Audience Manager-Daten hinzuzufügen und von der Experience Platform [Segmentation Service](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md) zu profitieren.

In Audience Manager können Sie Experience Platform-Segmente für Anwendungsfälle der Data Management Platform verwenden, z. B.:
* Fügen Sie [Drittanbieterdaten](/help/using/overview/data-types-collected.md#third-party-data) zu Ihren Segmenten hinzu.
* [Algorithmische Modellierung](/help/using/features/algorithmic-models/understanding-models.md);
* Aktivieren Sie Ihre Segmente für Ziele, die noch nicht im Zielkatalog der Experience Platform [unterstützt werden](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

Darüber hinaus werden Ihre Experience Platform-Segmente über [Core Services](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html) für andere Experience Cloud-Lösungen freigegeben.

>[!IMPORTANT]
>
> * Sie benötigen eine Audience Manager-Lizenz, um die oben genannten Anwendungsfälle der Data Management Platform zu aktivieren.
> * Sie *benötigen keine* Audience Manager-Lizenz, um Experience Platform-Segmente über die Core Services-Integration für Adobe Advertising Cloud, Adobe Target, Marketo und andere Experience Cloud-Lösungen freizugeben.


Eine Übersicht der Anwendungsfälle für die Zielgruppenfreigabe finden Sie in der unten stehenden Tabelle:

| **Anwendungsfall** | **Adobe Experience Platform** | **Audience Manager** | **Zentrale Dienste** |
---------|----------|---------|---------|
| **Zielgruppenfreigabe** | <ul><li>Kundenprofile mit Audience Manager-Daten anreichern</li><li>Audience Manager-Daten in Experience Platform-Segmentierung verwenden</li></ul> | <ul><li>Hinzufügen von Drittanbieterdaten zu Segmenten</li><li>Algorithmische Modellierung</li><li>Aktivierung an zusätzlichen Zielen</li></ul> | Verwenden Sie Experience Platform-Segmente in anderen Experience Cloud-Lösungen wie Adobe Target, Advertising Cloud oder Marketo. |

{style=&quot;table-layout:auto&quot;}

## Audience Manager-Segmente und -Eigenschaften in Adobe Experience Platform {#aam-segments-traits-in-aep}

Ihre Audience Manager-Eigenschaften und -Segmente werden in Experience Platform als **Zielgruppen** im Segmentarbeitsablauf angezeigt. Weitere Informationen zu Ihren Audience Manager-Segmenten und -Eigenschaften in Experience Platform finden Sie unter:

* [Übersicht über den Segmentierungsdienst](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Benutzerhandbuch zu Experience Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

## Adobe Experience Platform-Segmente in Audience Manager {#aep-segments-in-aam}

Segmente, die Sie in Experience Platform erstellen, werden in Ihrer Audience Manager-Oberfläche als Signale, Eigenschaften und Segmente mit den folgenden Kompositionsregeln angezeigt:

* Signal: Für jedes Segmentsegment der Experience Platform sollten Signale im Formular `segID = segment ID` angezeigt werden.
* Eigenschaft: Die Eigenschaftsregel ist die ID des Experience Platform-Segments.
* Segment: Das Segment besteht aus der oben beschriebenen Eigenschaft.

### Signale {#aep-segments-as-aam-signals}

Wählen Sie **[!UICONTROL Audience Data > Signals > General Online Data]** und suchen Sie nach `SegId`, um Signale aus der Experience Platform zu finden. Sie können diesen Bildschirm zu Debugging-Zwecken verwenden, um zu überprüfen, ob die Integration zwischen Experience Platform und Audience Manager korrekt eingerichtet wurde.

![Siehe Experience Platform-Signale im Audience Manager im Signale-Dashboard](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Eigenschaften {#aep-segments-as-aam-traits}

Audience Manager erstellt in Ihrem Eigenschaftsspeicher automatisch einen Eigenschaftsordner mit dem Namen **Experience Platform Traits**.

![Eigenschaften aus dem Experience Platformen-Dashboard](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Sie können automatisch erstellte Eigenschaften in Segmenten zusammen mit anderen Eigenschaften verwenden. Sie können beispielsweise Eigenschaften, die aus Experience Platform-Segmenten erstellt wurden, mit Eigenschaften von Drittanbietern kombinieren, die über das [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md) erfasst wurden.

Ein Beispiel für eine Eigenschaft, die automatisch aus einem Experience Platform-Segment erstellt wurde, finden Sie im folgenden Screenshot:

![Eigenschaft aus Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Artikelnummer | Name | Beschreibung |
---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Aus Experience Platform-Segmenten erstellte Eigenschaften werden als integrierte Eigenschaften in Audience Manager erstellt. |
| 2 | [!UICONTROL Data Source] | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus Experience Platform-Segmenten erstellt werden, werden in der Datenquelle **[!UICONTROL Adobe Experience Platform Audience Sharing]** gespeichert. |
| 3 | [!UICONTROL Integration Code] | Der Integrationscode entspricht der Segment-ID in Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | Der Eigenschaftsausdruck ist `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Ein automatisch erstelltes Segment, das diese Eigenschaft als Komposition verwendet. |

{style=&quot;table-layout:auto&quot;}

### Segmente {#aep-segments-as-aam-segments}

Audience Manager erstellt in Ihrem Segmentspeicher automatisch einen Segmentordner mit dem Namen **Experience Platform Segments**.

![Screenshot des Dashboards](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Ein Beispiel für ein Segment, das automatisch aus einem Segmentsegment der Experience Platform erstellt wurde, finden Sie im folgenden Screenshot:

![Screenshot des Segments](/help/using/integration/integration-aep/assets/aep-segment.png)

| Artikelnummer | Name | Beschreibung |
---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | Der Integrationscode entspricht der Segment-ID in Experience Platform. |
| 2 | [!UICONTROL Data Source] | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus Experience Platform-Segmenten erstellt werden, werden in der Datenquelle **[!DNL Adobe Experience Platform Audience Sharing]** gespeichert. |
| 1 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** gibt an, dass automatisch erstellte Segmente der in Experience Platform festgelegten Zusammenführungsrichtlinie entsprechen. |
| 4 | [!UICONTROL Segment Rule] | Das Segment besteht aus der Eigenschaft, die im Abschnitt [Eigenschaften](#aep-segments-as-aam-traits) beschrieben wird. |

{style=&quot;table-layout:auto&quot;}

## Unterstützung der Audience Manager-Datenexportkontrolle in Experience Platform {#aam-data-export-control-in-aep}

Um die Datennutzungskonformität in Experience Platform durchzusetzen, müssen alle entsprechenden Datensätze und Felder mit entsprechenden [Datennutzungsbezeichnungen](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html) versehen werden. Darüber hinaus müssen [Datennutzungsrichtlinien](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) für bestimmte Marketing-Aktionen für diese Beschriftungen aktiviert werden, wie im [DULE-Framework (Data Usage Labeling and Enforcement)](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework) beschrieben.

Im Prozess der Zielgruppenfreigabe zwischen Audience Manager und Experience Platform werden alle Datenexportkontrollen, die auf Audience Manager-Segmente angewendet wurden, in entsprechende Beschriftungen und Marketing-Aktionen übersetzt, die von Experience Platform Data Governance erkannt werden, und umgekehrt.

>[!NOTE]
>
>Allgemeine Informationen zu Datenexportkontrollen finden Sie in der [Dokumentation zur Datenexportkontrolle](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html).
>
>Dieses Dokument bietet eine Referenz dazu, wie bestimmte Audience Manager-Datenexportkontrollen den Datennutzungsbezeichnungen und Marketing-Aktionen in Platform zugeordnet werden.

### Datenexportkontrollen zu Datennutzungsbezeichnungen

In der folgenden Tabelle wird erläutert, wie bestimmte Datenexportkontrollen erkannten Datennutzungsbezeichnungen zugeordnet werden:

| Datenexportkontrolle | Datennutzungsbezeichnung |
| --- | --- |
| Kann nicht mit persönlich identifizierbaren Informationen verwendet werden | C3: Daten können nicht mit direkt identifizierbaren Informationen kombiniert oder anderweitig verwendet werden |
| Kann nicht für Offsite-Anzeigen-Targeting verwendet werden | C5: Daten können nicht für interessensbasiertes, Site-übergreifendes Targeting von Inhalten oder Anzeigen verwendet werden |
| Kann nicht für Onsite-Anzeigen-Targeting verwendet werden | C6: Daten können nicht für das On-site-Anzeigen-Targeting verwendet werden |
| Kann nicht für die Personalisierung vor Ort verwendet werden | C7: Daten können nicht für das On-site-Targeting von Inhalten verwendet werden |

{style=&quot;table-layout:auto&quot;}

### Datenexportkontrollen für Marketing-Aktionen

In der folgenden Tabelle wird beschrieben, wie bestimmte Datenexport-Beschriftungen erkannten Marketing-Aktionen zugeordnet werden:

| Datenexportbezeichnung | Marketing-Aktion |
| --- | --- |
| Dieses Ziel kann eine Kombination mit persönlich identifizierbaren Informationen (PII) ermöglichen | Kombinieren mit PII |
| Dieses Ziel kann für Offsite-Anzeigen-Targeting verwendet werden | Site-übergreifendes Targeting |
| Dieses Ziel kann für On-site-Anzeigen-Targeting verwendet werden | Onsite-Werbung |
| Dieses Ziel kann für die On-site-Anzeigenpersonalisierung verwendet werden | Onsite-Personalisierung |

{style=&quot;table-layout:auto&quot;}

## Grundlegendes zu Segmentpopulationsunterschieden zwischen Audience Manager und Experience Platform {#aep-aam-segment-population-differences}

Die Segmentpopulationszahlen können je nach Audience Manager- und Experience Platform-Segmenten variieren. Während Segmentzahlen für ähnliche oder identische Zielgruppen nahe liegen sollten, können die Unterschiede in Populationen auf die unten aufgeführten Faktoren zurückzuführen sein.

### Segmentbewertung in Experience Platform

Audience Manager aktualisiert die Berichtsnummern in der Benutzeroberfläche einmal täglich.   Der Zeitpunkt dieser Aktualisierung stimmt selten mit dem Zeitpunkt der Segmentbewertung in Experience Platform überein.

### Unterschiede zwischen Profilzusammenführungsrichtlinien und Zusammenführungsrichtlinien

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) in Audience Manager und  [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) in Experience Platform anders funktionieren und das für die einzelnen Komponenten verwendete Identitätsdiagramm variiert. Daher werden einige Unterschiede zwischen Segmentpopulationen erwartet.

### Segmentzusammenstellung in Experience Platform

Die Integration zwischen Adobe Experience Platform und Audience Manager teilt für alle Kunden eine Reihe von standardmäßigen [Identitäts-Namespaces](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types): ECID, IDFA, GAID, Hash-E-Mail-Adressen (EMAIL_LC_SHA256), AdCloud ID. Wenn Ihre Experience Platform- eine dieser Eigenschaften als primäre Identität für die qualifizierten Profile verwenden, werden die Profile in den Eigenschaften und Segmenten des Audience Managers gezählt.

>[!NOTE]
>
> Zielgruppen in Experience Platform mit Identitäten, die aus rohen E-Mails stammen, werden in Audience Manager nie angezeigt.

Wenn Sie beispielsweise über das Experience Platform-Segment &quot;Alle meine Kunden&quot;verfügen und die qualifizierten  CRM-IDs, ECID, IDFA, Roh- und Hash-E-Mail-Adressen sind, enthält das entsprechende Segment in Audience Manager nur Profile, die von ECID-, IDFA- und Hash-E-Mail-Adressen abgeleitet wurden. Die Segmentpopulation in Audience Manager wäre kleiner als die in Experience Platform.

![Experience Platform zur Segmentfreigabe in Audience Managern - Segmentzusammenstellung](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Übersicht über den Segmentierungsdienst](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Benutzerhandbuch zu Experience Platform Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)


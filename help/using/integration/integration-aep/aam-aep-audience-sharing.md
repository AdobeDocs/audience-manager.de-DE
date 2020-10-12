---
description: In diesem Artikel wird beschrieben, wie Audiencen von Audience Manager und Adobe Experience Platform gemeinsam genutzt werden.
seo-description: In diesem Artikel wird beschrieben, wie Audiencen von Audience Manager und Adobe Experience Platform gemeinsam genutzt werden.
seo-title: Freigabe von Zielgruppen zwischen Audience Manager und Adobe Experience Platform
solution: Audience Manager
title: Freigabe von Zielgruppen zwischen Audience Manager und Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
feature: Integration with Platform
translation-type: tm+mt
source-git-commit: 59eda3fa250fa33ef283f09b0027845431e9517b
workflow-type: tm+mt
source-wordcount: '1485'
ht-degree: 2%

---


# Segmentfreigabe für Experience Platformen mit Audience Manager und anderen Experience Cloud-Lösungen {#aam-aep-audience-sharing}

>[!NOTE]
>
> Wenden Sie sich an Ihren Vertriebsmitarbeiter, um den Zugriff auf diese Adobe freizugeben.

## Überblick {#overview}

Mit der Audience Sharing-Funktion zwischen Audience Manager und Adobe Experience Platform können Sie Ihre Audience Manager-Eigenschaften und -Segmente für Adobe Experience Platform und umgekehrt freigeben. Sie benötigen das [[!DNL Audience Manager Connector]](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) , um die Freigabe von Audiencen zwischen Audience Manager und Adobe Experience Platform zu aktivieren.

Sie können Audience Manager-Eigenschaften und -Segmente in der Experience Platform verwenden, um Ihren Kundendaten Audience Manager-Profilen hinzuzufügen und vom Experience Platform- [Segmentierungsdienst](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)zu profitieren.

In Audience Manager können Sie Experience Platformen-Segmente für Anwendungsfälle der Data Management Plattform verwenden, z. B.:
* Daten von [Drittanbietern](/help/using/overview/data-types-collected.md#third-party-data) zu Ihren Segmenten Hinzufügen;
* [Algorithmische Modellierung](/help/using/features/algorithmic-models/understanding-models.md);
* Aktivieren Sie Ihre Experience Platformen zu Zielen, die noch nicht im [Zielkatalog](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)unterstützt werden.

Darüber hinaus werden Ihre Experience Platformen über die [Hauptdienste](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)für andere Experience Cloud-Lösungen freigegeben.

>[!IMPORTANT]
>
> * Sie benötigen eine Audience Manager-Lizenz, um die oben genannten Anwendungsfälle für die Data Management-Plattform zu aktivieren.
> * Sie benötigen *keine Audience Manager-Lizenz, um Experience Platformen mit Adobe Ad Cloud, Adobe Target und anderen Experience Cloud-Lösungen über die Core Services-Integration freizugeben* .


<br> 

Die nachstehende Tabelle gibt einen Überblick über Anwendungsfälle für die Freigabe von Audiencen:

| **Anwendungsfall** | **Adobe Experience Platform** | **Audience Manager** | **Zentrale Dienste** |
---------|----------|---------|---------
| **Freigabe von Audiencen** | <ul><li>Aufwerten von Profilen mit Audience Manager-Daten</li><li>Audience Manager-Daten in der Segmentierung von Experience Platformen verwenden</li></ul> | <ul><li>Daten von Drittanbietern in Segmente Hinzufügen</li><li>Algorithmische Modellierung</li><li>Aktivierung zu weiteren Zielen</li></ul> | Verwenden Sie Experience Platformen-Segmente in anderen Experience Cloud-Lösungen, z. B. Adobe Target oder Analytics. |

<br> 

## Segmente und Eigenschaften von Audience Managern in Adobe Experience Platform {#aam-segments-traits-in-aep}

Ihre Audience Manager-Eigenschaften und -Segmente werden in Experience Platform als **Audiencen** im Segmentarbeitsablauf angezeigt. Weitere Informationen zu Audience Manager-Segmenten und -Eigenschaften in der Experience Platform finden Sie unter:

* [Übersicht über den Segmentdienst](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Benutzerhandbuch zum Segmentaufbau in der Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Adobe Experience Platform-Segmente in Audience Manager {#aep-segments-in-aam}

Segmente, die Sie in Experience Platform erstellen, werden in der Benutzeroberfläche Ihres Audience Managers als Signale, Eigenschaften und Segmente mit den folgenden Satzregeln angezeigt:

* Signal: Für jedes Experience Platformen-Segment sollten Sie die Signale im Formular sehen `segID = segment ID`.
* Eigenschaft: Die Eigenschaftsregel ist die ID des Segments Experience Platform.
* Segment: Das Segment besteht aus der oben beschriebenen Eigenschaft.

### Signale {#aep-segments-as-aam-signals}

Wählen Sie **[!UICONTROL Audience Data > Signals > General Online Data]** und suchen Sie nach `SegId` den Signalen, die von der Experience Platform kommen. Sie können diesen Bildschirm zum Debugging verwenden, um zu prüfen, ob die Integration zwischen Experience Platform und Audience Manager korrekt eingerichtet wurde.

![Siehe Experience Platformen im Audience Manager im Signal-Dashboard](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Eigenschaften {#aep-segments-as-aam-traits}

Audience Manager erstellt automatisch einen Eigenschaftsordner mit dem Namen **Experience Platformen-Eigenschaften** in der Datenspeicherung Eigenschaften.

![Eigenschaften aus dem Dashboard Experience Platform](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Sie können automatisch erstellte Eigenschaften in Segmenten neben anderen Eigenschaften verwenden. Sie können beispielsweise Eigenschaften, die aus Segmenten der Experience Platform erstellt wurden, mit Eigenschaften von Drittanbietern kombinieren, die über das [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md)erfasst wurden.

Ein Beispiel für eine Eigenschaft, die automatisch aus einem Segmentsegment der Experience Platform erstellt wurde, finden Sie im folgenden Screenshot:

![Eigenschaft aus Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Element Nr. | Name | Beschreibung |
---------|----------|---------
| 1 | [!UICONTROL Trait Type] | Eigenschaften, die aus Segmenten der Experience Platform erstellt wurden, werden als Eigenschaften an Bord in Audience Manager erstellt. |
| 2 | [!UICONTROL Data Source] | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus Segmenten der Experience Platform erstellt werden, werden in der Datenquelle gespeichert **[!UICONTROL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Integration Code] | Der Integrationscode entspricht der Segment-ID in der Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | Der Ausdruck der Eigenschaft ist `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Ein automatisch erstelltes Segment, das diese Eigenschaft als Komposition verwendet. |

<br> 

### Segmente {#aep-segments-as-aam-segments}

Audience Manager erstellt automatisch einen Segmentordner mit dem Namen **Experience Platform Segments** in Ihrer Segmentdatei.

![Screenshot des Dashboards](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Ein Beispiel eines Segments, das automatisch aus einem Segmentsegment erstellt wurde, finden Sie im folgenden Screenshot:

![Screenshot des Segments](/help/using/integration/integration-aep/assets/aep-segment.png)

| Element Nr. | Name | Beschreibung |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | Der Integrationscode entspricht der Segment-ID in der Experience Platform. |
| 2 | [!UICONTROL Data Source] | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus Segmenten der Experience Platform erstellt werden, werden in der Datenquelle gespeichert **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** gibt an, dass automatisch erstellte Segmente der in der Experience Platform festgelegten Zusammenführungsrichtlinie entsprechen. |
| 4 | [!UICONTROL Segment Rule] | Das Segment besteht aus den Eigenschaften, die im Abschnitt &quot; [Eigenschaften&quot;beschrieben werden](#aep-segments-as-aam-traits). |

## Audience Manager Data Export Control-Unterstützung für Experience Platform {#aam-data-export-control-in-aep}

Um die Einhaltung der Datenverwendungsvorschriften in der Experience Platform durchzusetzen, müssen alle entsprechenden Datensätze und Felder mit entsprechenden [Datenverwendungsbeschriftungen versehen](https://docs.adobe.com/content/help/en/experience-platform/data-governance/labels/overview.html)werden. Darüber hinaus müssen [Datenverwendungsrichtlinien](https://docs.adobe.com/content/help/en/experience-platform/data-governance/policies/overview.html) für spezifische Marketingaktionen für diese Beschriftungen aktiviert werden, wie im [Data Usage Labelling and Enforcement (DULE) Framework](https://docs.adobe.com/content/help/en/experience-platform/data-governance/home.html#dule-framework)beschrieben.

Beim Austausch von Audiencen zwischen Audience Manager und Experience Platform werden alle Datenexportsteuerelemente, die auf Audience Manager angewendet wurden, in entsprechende Beschriftungen und Marketingaktionen übersetzt, die von der Experience Platform Data Governance erkannt werden, und umgekehrt.

>[!NOTE]
>
>Allgemeine Informationen zu Datenexportkontrollen finden Sie in der Dokumentation [zu den](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)Datenexportkontrollen.
>
>Dieses Dokument bietet eine Referenz dafür, wie bestimmte Datenexportsteuerelemente des Audience Managers mit Datenverwendungsbeschriftungen und Marketingaktionen in der Plattform verknüpft sind.

### Datenexport-Steuerelemente in Datenverwendungsbeschriftungen

Die folgende Tabelle zeigt, wie bestimmte Datenexportsteuerelemente den erkannten Datenverwendungsbeschriftungen zugeordnet werden:

| Datenexportkontrolle | Datenverwendungsbeschriftung |
| --- | --- |
| Kann nicht mit persönlichen identifizierbaren Informationen verwendet werden | C3: Daten können nicht mit direkt identifizierbaren Informationen kombiniert oder anderweitig verwendet werden |
| Kann nicht für Offsite-Anzeigen-Targeting verwendet werden | C5: Daten können nicht für interessensbasiertes, seitenübergreifendes Targeting von Inhalten oder Anzeigen verwendet werden |
| Kann nicht für Onsite-Anzeigen-Targeting verwendet werden | C6: Daten können nicht für das Targeting von Onsite-Anzeigen verwendet werden |
| Kann nicht für die Personalisierung vor Ort verwendet werden | C7: Daten können nicht für das Targeting von Inhalten auf der Site verwendet werden |

### Datenexport-Steuerelemente in Marketingaktionen

Die folgende Tabelle zeigt, wie bestimmte Datenexportbeschriftungen den erkannten Marketingaktionen zugeordnet werden:

| Datenexportbeschriftung | Marketingaktion |
| --- | --- |
| Dieses Ziel kann eine Kombination mit personenbezogenen Daten (PII) ermöglichen | Kombination mit PII |
| Dieses Ziel kann für Offsite-Anzeigen-Targeting verwendet werden | Site-übergreifendes Targeting |
| Dieses Ziel kann für Onsite-Anzeigen-Targeting verwendet werden | Onsite-Werbung |
| Dieses Ziel kann für die Personalisierung von Onsite-Anzeigen verwendet werden | Onsite-Personalisierung |

## Segmentpopulationsunterschiede zwischen Audience Manager und Experience Platform verstehen {#aep-aam-segment-population-differences}

Die Segmentpopulationszahlen können je nach Audience Manager- und Experience Platform-Segment variieren. Während Segmentzahlen für ähnliche oder identische Audiencen nahe liegen sollten, können Populationsunterschiede auf die unten aufgeführten Faktoren zurückzuführen sein.

### Segmentbewertung in Experience Platform

Audience Manager aktualisiert die Berichte-Nummern in der Benutzeroberfläche einmal täglich.   Der Zeitpunkt dieser Aktualisierung passt sich selten dem Zeitpunkt der Segmentbewertung in der Experience Platform an.

### Unterschiede zwischen Profil Merge Rules und Merge Policies

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) in Audience Manager und [[!UICONTROL Merge Policies]](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) in Experience Platform unterschiedlich funktionieren und das für jede Version verwendete Identitätsdiagramm variiert. Daher werden einige Unterschiede zwischen Segmentpopulationen erwartet.

### Segmentzusammensetzung in Experience Platform

Die Integration zwischen Adobe Experience Platform und Audience Manager nutzt eine Reihe von standardmäßigen [Identitäts-Namensräumen](https://docs.adobe.com/content/help/en/experience-platform/identity/namespaces.html#identity-types) für alle Kunden: ECID, IDFA, GAID, Hash-E-Mail-Adressen (EMAIL_LC_SHA256), AdCloud ID usw. Wenn Ihre Experience Platformen-Segmente eine dieser ID als primäre Identität für die qualifizierten Profil verwenden, werden die Profil in Audience Manager- und Segmenteigenschaften gezählt.

Darüber hinaus kann Audience Manager die eingehenden Realisierungen für alle benutzerdefinierten Identitäts-Namensraum registrieren, die Sie in Experience Platformen-Segmenten verwenden, wenn Sie bereits über eine entsprechende Datenquelle im Audience Manager verfügen, die von dieser ID ausgefüllt wurde.

>[!NOTE]
>
> Audiencen in Experience Platform mit IDs, die aus unbearbeiteten E-Mails herausgegeben werden, werden in Audience Manager nie angezeigt.

Wenn Sie z. B. das Segment &quot;Alle meine Kunden&quot;mit einer Experience Platform versehen haben und die qualifizierten Profil CRM-IDs, ECID, IDFA, Roh- und Hash-E-Mail-Adressen sind, umfasst das entsprechende Segment in Audience Manager nur Profil, die mit CRM-IDs, ECID, IDFA und Hash-E-Mail-Adressen ausgefüllt wurden. Die Segmentpopulation in Audience Manager wäre kleiner als die in der Experience Platform.

![Experience Platform zur Segmentfreigabe in Audience Manager - Segmentzusammensetzung](/help/using/integration/integration-aep/assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Übersicht über den Segmentdienst](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Benutzerhandbuch zum Segmentaufbau in der Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
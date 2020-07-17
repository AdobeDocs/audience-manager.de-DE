---
description: In diesem Artikel wird beschrieben, wie Audiencen von Audience Manager und Adobe Experience Platform gemeinsam genutzt werden.
seo-description: In diesem Artikel wird beschrieben, wie Audiencen von Audience Manager und Adobe Experience Platform gemeinsam genutzt werden.
seo-title: Freigabe von Zielgruppen zwischen Audience Manager und Adobe Experience Platform
solution: Audience Manager
title: Freigabe von Zielgruppen zwischen Audience Manager und Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
feature: Integration with Platform
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1177'
ht-degree: 4%

---


# Freigabe von Zielgruppen zwischen Audience Manager und Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> Wenden Sie sich an Ihren Adobe-Vertriebsmitarbeiter, um den Zugriff auf diese Funktion freizugeben.

## Überblick {#overview}

Die Funktion zum Teilen von Audiencen zwischen Audience Manager und Adobe Experience Platform ermöglicht es Ihnen, Ihre Audience Manager-Eigenschaften und -Segmente für die Adobe Experience Platform und umgekehrt freizugeben. Sie benötigen den [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) , um die Freigabe von Audiencen zwischen Audience Manager und Adobe Experience Platform zu aktivieren.

Sie können Audience Manager-Eigenschaften und -Segmente in der Experience Platform verwenden, um Ihren Kundendaten Audience Manager-Profilen hinzuzufügen und vom Experience Platform- [Segmentierungsdienst](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)zu profitieren.

In Audience Manager können Sie Experience Platformen-Segmente für Anwendungsfälle der Data Management Plattform verwenden, z. B.:
* Daten von [Drittanbietern](/help/using/overview/data-types-collected.md#third-party-data) zu Ihren Segmenten Hinzufügen;
* [Algorithmische Modellierung](/help/using/features/algorithmic-models/understanding-models.md);
* Aktivieren Sie Ihre Experience Platformen zu Zielen, die noch nicht im [Zielkatalog](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)unterstützt werden.

Darüber hinaus werden Ihre Experience Platformen über die [Hauptdienste](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)für andere Experience Cloud-Lösungen freigegeben.

<br> 

Die nachstehende Tabelle gibt einen Überblick über Anwendungsfälle für die Freigabe von Audiencen:

| **Anwendungsfall** | **Adobe Experience Platform** | **Audience Manager** | **Zentrale Dienste** |
---------|----------|---------|---------
| **Freigabe von Audiencen** | <ul><li>Aufwerten von Profilen mit Audience Manager-Daten</li><li>Audience Manager-Daten in der Segmentierung von Experience Platformen verwenden</li></ul> | <ul><li>Daten von Drittanbietern in Segmente Hinzufügen</li><li>Algorithmische Modellierung</li><li>Aktivierung zu weiteren Zielen</li></ul> | Verwenden Sie Experience Platformen-Segmente in anderen Experience Cloud-Lösungen, wie z. B. Adobe Target oder Analytics. |

<br> 

## Segmente und Eigenschaften von Audience Managern in Adobe Experience Platform {#aam-segments-traits-in-aep}

Ihre Audience Manager-Eigenschaften und -Segmente werden in Experience Platform als **Audiencen** im Segmentarbeitsablauf angezeigt. Weitere Informationen zu Audience Manager-Segmenten und -Eigenschaften in der Experience Platform finden Sie unter:

* [Übersicht über den Segmentdienst](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Benutzerhandbuch zum Segmentaufbau in der Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Adobe Experience Platformen in Audience Manager {#aep-segments-in-aam}

Segmente, die Sie in Experience Platform erstellen, werden auf der Benutzeroberfläche des Audience Managers als Eigenschaften und Segmente mit den folgenden Satzregeln angezeigt:
* Eigenschaft: Die Eigenschaftsregel ist die ID des Segments Experience Platform.
* Segment: Das Segment besteht aus der oben beschriebenen Eigenschaft.

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

>[!NOTE] Allgemeine Informationen zu Datenexportkontrollen finden Sie in der Dokumentation [zu den](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html)Datenexportkontrollen.
Dieses Dokument bietet eine Referenz dafür, wie bestimmte Datenexportsteuerelemente des Audience Managers mit Datenverwendungsbeschriftungen und Marketingaktionen in der Plattform verknüpft sind.

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

## Segmentpopulationsunterschiede zwischen Audience Manager und Experience Platform verstehen

Die Segmentpopulationszahlen können je nach Audience Manager- und Experience Platform-Segment variieren. Während Segmentzahlen für ähnliche oder identische Audiencen nahe liegen sollten, können Populationsunterschiede auf Folgendes zurückzuführen sein:

* Laufzeit von Segmentierungsaufträgen Audience Manager führt einen Segmentierungsauftrag aus, der die Nummern in der Oberfläche einmal täglich aktualisiert. Dieser Auftrag passt sich selten an die Segmentierungsaufträge in der Experience Platform an.
* [Profil Merge Rules](/help/using/features/profile-merge-rules/merge-rules-overview.md) in Audience Manager- und [Merge-Richtlinien](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) in der Experience Platform funktionieren unterschiedlich, und das für jede Version verwendete Identitätsdiagramm ist unterschiedlich. Daher werden einige Unterschiede zwischen Segmentpopulationen erwartet.

>[!MORELIKETHIS]
>
>* [Übersicht über den Segmentdienst](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Benutzerhandbuch zum Segmentaufbau in der Experience Platform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
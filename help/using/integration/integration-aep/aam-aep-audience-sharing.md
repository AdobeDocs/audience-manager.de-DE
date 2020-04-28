---
description: In diesem Artikel wird beschrieben, wie Audiencen zwischen Audience Manager und Adobe Experience Platform freigegeben werden.
seo-description: In diesem Artikel wird beschrieben, wie Audiencen zwischen Audience Manager und Adobe Experience Platform freigegeben werden.
seo-title: Freigabe von Audiencen zwischen Audience Manager und Adobe Experience Platform
solution: Audience Manager
title: Freigabe von Audiencen zwischen Audience Manager und Adobe Experience Platform
keywords: AEP audience sharing, AEP segments, Platform segments, segment sharing, audience sharing, share segments
translation-type: tm+mt
source-git-commit: f191035a1ad4b83bb3d391de80e1f925d6295df7

---


# Freigabe von Audiencen zwischen Audience Manager und Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
> Wenden Sie sich an Ihren Adobe-Vertriebsmitarbeiter, um den Zugriff auf diese Funktion freizugeben.

## Überblick {#overview}

Mit der Audience Sharing-Funktion von Audience Manager und Adobe Experience Platform können Sie Ihre Audience Manager-Eigenschaften und -Segmente für Adobe Experience Platform freigeben und umgekehrt. Sie benötigen den [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html) , um die Freigabe von Audiencen zwischen Audience Manager und Adobe Experience Platform zu aktivieren.

Sie können Audience Manager-Eigenschaften und -Segmente in Experience Platform verwenden, um Audience Manager-Daten zu Ihren Profilen hinzuzufügen und den Experience Platform- [Segmentierungsdienst](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segmentation-overview.md)zu nutzen.

In Audience Manager können Sie Experience Platform-Segmente für Anwendungsfälle der Data Management-Plattform verwenden, z. B.:
* Daten von [Drittanbietern](/help/using/overview/data-types-collected.md#third-party-data) zu Ihren Segmenten Hinzufügen;
* [Algorithmische Modellierung](/help/using/features/algorithmic-models/understanding-models.md);
* Aktivieren Sie Ihre Segmente zu Zielen, die noch nicht im Experience Platform- [Zielkatalog](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html)unterstützt werden.

Darüber hinaus werden Ihre Experience Platform-Segmente über [Hauptdienste](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)für andere Experience Cloud-Lösungen freigegeben.

<br> 

Die nachstehende Tabelle gibt einen Überblick über Anwendungsfälle für die Freigabe von Audiencen:

| **Nutzungsszenario** | **Adobe Experience Platform** | **Audience Manager** | **Zentrale Dienste** |
---------|----------|---------|---------
| **Freigabe von Audiencen** | <ul><li>Kundendaten mit Audience Manager erweitern</li><li>Audience Manager-Daten in der Segmentierung der Experience Platform verwenden</li></ul> | <ul><li>Daten von Drittanbietern in Segmente Hinzufügen</li><li>Algorithmische Modellierung</li><li>Aktivierung zu weiteren Zielen</li></ul> | Verwenden Sie Experience Platform-Segmente in anderen Experience Cloud-Lösungen, z. B. Adobe Zielgruppe oder Analytics. |

<br> 

## Segmente und Eigenschaften von Audience Manager in Adobe Experience Platform {#aam-segments-traits-in-aep}

Ihre Audience Manager-Eigenschaften und -Segmente werden in Experience Platform als **Audiencen** im Segmentarbeitsablauf angezeigt. Weitere Informationen zu den Segmenten und Eigenschaften von Audience Manager in Experience Platform finden Sie unter:

* [Übersicht über den Segmentdienst](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
* [Benutzerhandbuch zum Segmentaufbau in der Erlebnisplattform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

<br> 

## Segmente der Adobe Experience Platform in Audience Manager {#aep-segments-in-aam}

Segmente, die Sie in Experience Platform erstellen, werden auf der Benutzeroberfläche von Audience Manager als Eigenschaften und Segmente mit den folgenden Satzregeln angezeigt:
* Eigenschaft: Die Eigenschaftsregel ist die ID des Segments Erlebnisplattform.
* Segment: Das Segment besteht aus der oben beschriebenen Eigenschaft.

### Eigenschaften {#aep-segments-as-aam-traits}

Audience Manager erstellt automatisch einen Eigenschaftsordner mit dem Namen **Experience Platform-Eigenschaften** in Ihrer Eigenschafts-Datenspeicherung.

![Eigenschaften aus Experience Platform Dashboard](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Sie können automatisch erstellte Eigenschaften in Segmenten neben anderen Eigenschaften verwenden. Sie können beispielsweise Eigenschaften, die aus Experience Platform-Segmenten erstellt wurden, mit Eigenschaften von Drittanbietern kombinieren, die über den [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md)erworben wurden.

Ein Beispiel für eine Eigenschaft, die automatisch aus einem Experience Platform-Segment erstellt wurde, finden Sie im folgenden Screenshot:

![Eigenschaften aus Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Element Nr. | Name | Beschreibung |
---------|----------|---------
| 1 | Eigenschaftstyp | Eigenschaften, die aus Experience Platform-Segmenten erstellt wurden, werden als integrierte Eigenschaften in Audience Manager erstellt. |
| 2 | Datenquelle | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus Experience Platform-Segmenten erstellt werden, werden in der Datenquelle **Adobe Experience Platform Audience Sharing** gespeichert. |
| 3 | Integrationscode | Der Integrationscode entspricht der Segment-ID in Experience Platform. |
| 4 | Eigenschaften-Ausdruck | Der Ausdruck der Eigenschaft ist `segID = segment ID in Experience Platform`. |
| 5 | Segmente mit dieser Eigenschaft | Ein automatisch erstelltes Segment, das diese Eigenschaft als Komposition verwendet. |

<br> 

### Segmente {#aep-segments-as-aam-segments}

Audience Manager erstellt automatisch einen Segmentordner mit dem Namen **Experience Platform-Segmente** in Ihrer Segment-Datenspeicherung.

![Screenshot des Dashboards](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Ein Beispiel für ein Segment, das automatisch aus einem Experience Platform-Segment erstellt wurde, finden Sie im folgenden Screenshot:

![Screenshot des Segments](/help/using/integration/integration-aep/assets/aep-segment.png)

| Element Nr. | Name | Beschreibung |
---------|----------|---------
| 1 | [!UICONTROL Integration Code] | Der Integrationscode entspricht der Segment-ID in Experience Platform. |
| 2 | [!UICONTROL Data Source] | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus Experience Platform-Segmenten erstellt werden, werden in der Datenquelle gespeichert **[!DNL Adobe Experience Platform Audience Sharing]**. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** gibt an, dass automatisch erstellte Segmente der in Experience Platform festgelegten Richtlinie für die Zusammenführung entsprechen. |
| 4 | [!UICONTROL Segment Rule] | Das Segment besteht aus den Eigenschaften, die im Abschnitt &quot; [Eigenschaften&quot;beschrieben werden](#aep-segments-as-aam-traits). |

## Unterschiede bei der Segmentpopulation zwischen Audience Manager und Experience Platform verstehen

Die Anzahl der Segmentpopulationen kann je nach Audience Manager- und Erlebnisplattformsegment variieren. Während Segmentzahlen für ähnliche oder identische Audiencen nahe liegen sollten, können Populationsunterschiede auf Folgendes zurückzuführen sein:

* Laufzeit von Segmentierungsaufträgen Audience Manager führt einen Segmentierungsauftrag aus, mit dem die Zahlen in der Oberfläche einmal täglich aktualisiert werden. Dieser Auftrag wird selten an den Segmentierungsaufträgen in Experience Platform ausgerichtet.
* [Profil Merge Rules](/help/using/features/profile-merge-rules/merge-rules-overview.md) in Audience Manager und [Merge Policies](https://docs.adobe.com/content/help/en/experience-platform/profile/ui/merge-policies.html) in Experience Platform funktionieren anders, und das für jede Version verwendete Identitätsdiagramm ist unterschiedlich. Daher werden einige Unterschiede zwischen Segmentpopulationen erwartet.


>[!MORELIKETHIS]
>
>* [Übersicht über den Segmentdienst](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html#audiences)
>* [Benutzerhandbuch zum Segmentaufbau in der Erlebnisplattform](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager Connector](https://docs.adobe.com/content/help/en/experience-platform/sources/connectors/adobe-applications/audience-manager.html)



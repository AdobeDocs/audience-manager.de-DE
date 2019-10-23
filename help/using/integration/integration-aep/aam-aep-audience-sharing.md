---
description: In diesem Artikel wird beschrieben, wie Zielgruppen von Audience Manager und Adobe Experience Platform gemeinsam genutzt werden.
seo-description: In diesem Artikel wird beschrieben, wie Zielgruppen von Audience Manager und Adobe Experience Platform gemeinsam genutzt werden.
seo-title: Zielgruppenfreigabe zwischen Audience Manager und Adobe Experience Platform
solution: Audience Manager
title: Zielgruppenfreigabe zwischen Audience Manager und Adobe Experience Platform
keywords: Freigabe von AEP-Zielgruppen, AEP-Segmente, Plattformsegmente
translation-type: tm+mt
source-git-commit: 421f15b79fa647bf4fbf71a425c7f7792fb302e5

---


# Zielgruppenfreigabe zwischen Audience Manager und Adobe Experience Platform {#aam-aep-audience-sharing}

>[!NOTE]
>
>Diese Seite enthält eine Beta-Dokumentation, in der die Funktionen beschrieben werden, die Kunden von Audience Manager *und* Adobe Experience Platform zur Verfügung stehen. Diese Dokumentation kann vor der endgültigen Produktversion geändert werden.
>
> Wenden Sie sich an Ihren Adobe-Vertriebsmitarbeiter, um den Zugriff auf diese Funktion freizugeben.

## Überblick {#overview}

Mit der Zielgruppenfreigabe-Funktion von Audience Manager und Adobe Experience Platform können Sie Ihre Audience Manager-Eigenschaften und -Segmente für Adobe Experience Platform freigeben und umgekehrt.

Sie können Audience Manager-Eigenschaften und -Segmente in Experience Platform verwenden, um Audience Manager-Daten zu Ihren Kundenprofilen hinzuzufügen und den Experience Platform- [Segmentierungsdienst](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)zu nutzen.

In Audience Manager können Sie Experience Platform-Segmente für Anwendungsfälle von Data Management Platform verwenden, z. B.:
* Hinzufügen von [Drittanbieterdaten](/help/using/overview/data-types-collected.md#third-party-data) zu Ihren Segmenten;
* [Algorithmische Modellierung](/help/using/features/algorithmic-models/understanding-models.md);
* Aktivieren von Segmenten zu Zielen, die derzeit nicht in der Experience Platform unterstützt werden.

Darüber hinaus werden Ihre Experience Platform-Segmente über [Hauptdienste](https://docs.adobe.com/content/help/en/core-services/interface/experience-cloud.html)für andere Experience Cloud-Lösungen freigegeben.

<br> 

Die nachstehende Tabelle gibt einen Überblick über Anwendungsfälle für die Freigabe von Zielgruppen:

| `*` | **Adobe Experience Platform** | **Audience Manager** | **Zentrale Dienste** |
---------|----------|---------|---------
| **Anwendungsfall für die Freigabe von Zielgruppen** | <ul><li>Kundenprofile mit Audience Manager-Daten erweitern</li><li>Verwenden von Audience Manager-Daten in der Segmentierung der Experience Platform</li></ul> | <ul><li>Daten von Drittanbietern zu Segmenten hinzufügen</li><li>Algorithmische Modellierung</li><li>Aktivierung zu weiteren Zielen</li></ul> | Verwenden Sie Experience Platform-Segmente in anderen Experience Cloud-Lösungen, z. B. Adobe Target oder Analytics. |

<br> 

## Audience Manager-Segmente und -Eigenschaften in Adobe Experience Platform {#aam-segments-traits-in-aep}

Ihre Audience Manager-Eigenschaften und -Segmente werden in Experience Platform als **Zielgruppen** im Segmentarbeitsablauf angezeigt. Weitere Informationen zu den Segmenten und Eigenschaften von Audience Manager in Experience Platform finden Sie unter:

* [Übersicht über den Segmentdienst](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segmentation.md)
* [Benutzerhandbuch zum Segmentaufbau in der Erlebnisplattform](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!end-user/markdown/segmentation_overview/segment-builder-guide.md)

<br> 

## Segmente der Adobe Experience Platform in Audience Manager {#aep-segments-in-aam}

Segmente, die Sie in Experience Platform erstellen, werden auf der Benutzeroberfläche von Audience Manager als Eigenschaften und Segmente mit den folgenden Satzregeln angezeigt:
* Eigenschaft: Die Eigenschaftsregel ist die ID des Segments Erlebnisplattform.
* Segment: Das Segment besteht aus der oben beschriebenen Eigenschaft.

### Eigenschaften {#aep-segments-as-aam-traits}

Audience Manager erstellt automatisch einen Eigenschaftsordner mit dem Namen **Experience Platform-Eigenschaften** im Eigenschaftsspeicher.

![Eigenschaften aus dem Experience Platform-Dashboard](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Sie können automatisch erstellte Eigenschaften in Segmenten neben anderen Eigenschaften verwenden. Sie können beispielsweise Eigenschaften, die aus Experience Platform-Segmenten erstellt wurden, mit Eigenschaften von Drittanbietern kombinieren, die über den [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md)erworben wurden.

Ein Beispiel für eine Eigenschaft, die automatisch aus einem Experience Platform-Segment erstellt wurde, finden Sie im folgenden Screenshot:

![Eigenschaften aus Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Element Nr. | Name | Beschreibung |
---------|----------|---------
| 1 | Eigenschaftstyp | Eigenschaften, die aus Experience Platform-Segmenten erstellt wurden, werden in Audience Manager als integrierte Eigenschaften erstellt. |
| 2 | Datenquelle | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus Experience Platform-Segmenten erstellt werden, werden in der Datenquelle **Adobe Experience Platform Audience Sharing** gespeichert. |
| 3 | Integrationscode | Der Integrationscode entspricht der Segment-ID in Experience Platform. |
| 4 | Eigenschaftsausdruck | Der Eigenschaftsausdruck ist `segID = segment ID in Experience Platform`. |
| 5 | Segmente mit dieser Eigenschaft | Ein automatisch erstelltes Segment, das diese Eigenschaft als Komposition verwendet. |

<br> 

### Segmente {#aep-segments-as-aam-segments}

Audience Manager erstellt automatisch einen Segmentordner mit dem Namen **Experience Platform-Segmente** im Segmentspeicher.

![Screenshot des Dashboards](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Ein Beispiel für ein Segment, das automatisch aus einem Experience Platform-Segment erstellt wurde, finden Sie im folgenden Screenshot:

![Screenshot des Segments](/help/using/integration/integration-aep/assets/aep-segment.png)

| Element Nr. | Name | Beschreibung |
---------|----------|---------
| 1 | Integrationscode | Der Integrationscode entspricht der Segment-ID in Experience Platform. |
| 2 | Datenquelle | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus Experience Platform-Segmenten erstellt werden, werden in der Datenquelle **Adobe Experience Platform Audience Sharing** gespeichert. |
| 3 | Regel zur Profilzusammenführung | **Die Richtlinie** für die externe Zusammenführung gibt an, dass automatisch erstellte Segmente der in Experience Platform festgelegten Richtlinie für die Zusammenführung entsprechen. |
| 4 | Segmentregel | Das Segment besteht aus den Eigenschaften, die im Abschnitt [Eigenschaften beschrieben werden](#aep-segments-as-aam-traits). |
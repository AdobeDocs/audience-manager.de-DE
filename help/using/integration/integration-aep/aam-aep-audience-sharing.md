---
description: Erfahren Sie, wie Sie die Datenfreigabe aktivieren und wie Zielgruppen zwischen Audience Manager und Adobe Experience Platform freigegeben werden
solution: Audience Manager
title: Experience Platform-Segmentfreigabe mit Audience Manager und anderen Experience Cloud-Lösungen
keywords: Freigabe von AEP-Zielgruppen, AEP-Segmente, Platform-Segmente, Segmentfreigabe, Zielgruppenfreigabe, Segmentfreigabe von AAM-AEP-Segmenten
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: d21d0574ee0338dbd5e11c60e0d64042182aa18b
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 1%

---

# Experience Platform-Segmentfreigabe mit Audience Manager und anderen Experience Cloud-Lösungen

## Überblick {#overview}

Mit der Funktion zur Freigabe von Audiences zwischen Audience Manager und Adobe Experience Platform können Sie Audience Manager-Eigenschaften und -Segmente für Adobe Experience Platform freigeben und Segmente für Audience Manager Experience Platform.

Sie benötigen die [[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html) und das Ziel [Experience Cloud-Zielgruppen](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html) in Experience Platform, um die Freigabe von Zielgruppen zwischen Audience Manager und Adobe Experience Platform zu aktivieren.

Sie können Audience Manager-Eigenschaften und -Segmente in Experience Platform verwenden, um Audience Manager-Daten zu Ihren Kundenprofilen hinzuzufügen und vom Experience Platform (Segmentierungs[Service) ](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en).

Im Audience Manager können Sie Experience Platform-Segmente für Anwendungsfälle der Data Management-Plattform verwenden, z. B.:
* Fügen Sie [ Segmente ](/help/using/overview/data-types-collected.md#third-party-data) Drittanbieterdaten hinzu.
* [Algorithmische Modellierung](/help/using/features/algorithmic-models/understanding-models.md);
* Aktivieren Sie Ihre Segmente für Ziele, die noch nicht im Experience Platform-Zielkatalog unterstützt [](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html).

Darüber hinaus werden Ihre Experience Platform-Segmente über &quot;[ Services“ für andere Experience Cloud-Lösungen ](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html).

>[!IMPORTANT]
>
> * Sie benötigen eine Audience Manager-Lizenz, um die oben genannten Anwendungsfälle der Data Management-Plattform zu aktivieren.
> * Sie *keine Audience Manager* Lizenz benötigen, um Experience Platform-Segmente über die Core Services-Integration mit Adobe Advertising Cloud, Adobe Target, Marketo und anderen Experience Cloud-Lösungen zu teilen.

In der folgenden Tabelle finden Sie einen Überblick über Anwendungsfälle für die Freigabe von Zielgruppen:

| **Nutzungsszenario** | **Adobe Experience Platform** | **Audience Manager** | **Zentrale Dienste** |
|---------|----------|---------|---------|
| **Audience Sharing** | <ul><li>Anreicherung von Kundenprofilen mit Audience Manager-Daten</li><li>Verwenden von Audience Manager-Daten in der Experience Platform-Segmentierung</li></ul> | <ul><li>Hinzufügen von Drittanbieterdaten zu Segmenten</li><li>Algorithmische Modellierung</li><li>Aktivierung für zusätzliche Ziele</li></ul> | Verwenden Sie Experience Platform-Segmente in anderen Experience Cloud-Lösungen wie Adobe Target, Advertising Cloud oder Marketo. |

{style="table-layout:auto"}

## Audience Manager-Segmente und -Eigenschaften in Adobe Experience Platform {#aam-segments-traits-in-aep}

In den folgenden Abschnitten wird beschrieben, wie Sie die Datenfreigabe von Audience Manager zu Experience Platform aktivieren und wie Sie Audience Manager-Eigenschaften und -Segmente in Experience Platform verwenden.

### Datenfreigabe vom Audience Manager zum Experience Platform aktivieren {#enable-aam-to-aep-data}

Um Segmente und Eigenschaften von Audience Manager an Experience Platform zu senden, müssen Sie den Audience Manager-Quell-Connector im Experience Platform-Quellkatalog einrichten. Dies ist ein Self-Service-Workflow, für den keine Beteiligung der Adobe-Kundenunterstützung oder der Entwicklungsteams erforderlich ist. Informationen zum Einrichten des Audience Manager-Quell-Connectors finden Sie unter:

* [Quelltext des Audience Managers ](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
* [Erstellen einer Adobe Audience Manager-Quellverbindung über die Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=en)

>[!IMPORTANT]
>
>Beim Adobe wird empfohlen, die Verbindung zu konfigurieren, ohne die **[!UICONTROL Select all segments]**- und **[!UICONTROL Select all traits]** wie unten dargestellt auszuwählen. Die Aufnahme umfangreicher Audience Manager-Segmentpopulationen hat einen direkten Einfluss auf Ihre Gesamtprofilanzahl, wenn Sie zum ersten Mal ein Audience Manager-Segment mithilfe der Audience Manager-Quelle an Platform senden. Das bedeutet, dass die Auswahl aller Segmente möglicherweise zu einer Profilanzahl führt, die über Ihrer Lizenznutzungsberechtigung liegt.
>
>![Screenshot, der die Optionen Alle Segmente auswählen und Alle Eigenschaften auswählen zeigt, die im Workflow für die Verbindung mit dem Audience Manager-Quell-Connector nicht aktiviert sind.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Verwenden von Audience Manager-Eigenschaften und -Segmenten beim Experience Platform {#use-aam-data-in-aep}

Nachdem Sie den Audience Manager-Quell-Connector zum Importieren von Eigenschaften und Segmenten aus Audience Manager eingerichtet haben, werden Ihre Segmentdaten im Audience Manager-Workflow als **Zielgruppen** im Experience Platform angezeigt. Weitere Informationen zu Audience Manager-Segmenten und -Eigenschaften in Experience Platform finden Sie unter:

* [Segmentierungs-Service - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
* [Experience Platform Segment Builder-Benutzerhandbuch](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)

## Adobe Experience Platform-Segmente im Audience Manager {#aep-segments-in-aam}

In den folgenden Abschnitten wird beschrieben, wie Sie die Datenfreigabe vom Experience Platform zum Audience Manager aktivieren und wie Sie Experience Platform-Segmente im Audience Manager verwenden.

### Datenfreigabe von Experience Platform zu Audience Manager aktivieren {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> In diesem Abschnitt wird die Integration der Segmentfreigabe vom Experience Platform zum Audience Manager beschrieben. Sie können diese Integration jetzt ohne Unterstützung von Adobe-Kundenbetreuern einrichten. Weitere Informationen finden Sie in der Zieldokumentation zum [Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html)Zielgruppen“.

>[!NOTE]
>
> Wenden Sie sich an Ihren Adobe Customer Success Manager oder die Kundenunterstützung, um den Zugriff auf diese Funktion zu entsperren.

Um Segmente von Experience Platform an Audience Manager zu senden, müssen Sie sich entweder an die Kundenunterstützung oder Ihren Customer Success Manager wenden. Die Teams der Kundenunterstützung und des Support-Managements müssen ein Ticket erstellen (siehe Vorlagenticket AAM-52354), um die Verbindung zwischen Platform und Audience Manager zu aktivieren.

Stellen Sie sicher, dass Sie Pläne für die Daten von Platform zu Audience Manager freigeben, um sicherzustellen, dass die Verbindung korrekt eingerichtet ist. Wenn beispielsweise regionale Daten für Segmente freigegeben werden sollen, die an Adobe Target gesendet werden, müssen diese Informationen im Ticket kommuniziert werden. Die Datenfreigabeverbindung von Experience Platform zu Audience Manager wird innerhalb von sechs Werktagen nach der Anforderung eingerichtet.

### Verwenden von Experience Platform-Segmenten im Audience Manager {#use-aep-data-in-aam}

Segmente, die Sie im Experience Platform erstellen, werden in Ihrer Audience Manager-Benutzeroberfläche als Signale, Eigenschaften und Segmente mit den folgenden Kompositionsregeln angezeigt:

* Signal: Für jedes Experience Platform-Segment sollten Signale im `segID = segment ID` angezeigt werden.
* Eigenschaft: Die Eigenschaftsregel ist die ID des Experience Platform-Segments.
* Segment: Das Segment besteht aus der oben beschriebenen Eigenschaft.

### Signale {#aep-segments-as-aam-signals}

Wählen Sie **[!UICONTROL Audience Data > Signals > General Online Data]** und suchen Sie nach `SegId`, um Signale zu finden, die von Experience Platform eingehen. Sie können diesen Bildschirm zum Debugging verwenden, um zu überprüfen, ob die Integration zwischen Experience Platform und Audience Manager korrekt eingerichtet wurde.

![Siehe Experience Platform-Signale im Audience Manager im Signale-Dashboard](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Eigenschaften {#aep-segments-as-aam-traits}

Audience Manager erstellt in Ihrem Eigenschaftsspeicher automatisch einen Eigenschaftsordner mit dem Namen **Experience Platform** Eigenschaften“.

![Eigenschaften aus dem Experience Platform-Dashboard](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Sie können automatisch erstellte Eigenschaften in Segmenten zusammen mit anderen Eigenschaften verwenden. Sie können beispielsweise Eigenschaften, die aus Experience Platform-Segmenten erstellt wurden, mit Eigenschaften von Drittanbietern mischen, die über die [Audience Marketplace erfasst ](/help/using/features/audience-marketplace/audience-marketplace.md).

Ein Beispiel für eine Eigenschaft, die automatisch aus einem Experience Platform-Segment erstellt wurde, finden Sie im folgenden Screenshot:

![Eigenschaft vom Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Artikelnummer | Name | Beschreibung |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Eigenschaften, die aus Experience Platform-Segmenten erstellt wurden, werden als integrierte Eigenschaften im Audience Manager erstellt. |
| 2 | [!UICONTROL Data Source] | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus dem Experience Platform von Segmenten erstellt werden, werden im **[!UICONTROL Adobe Experience Platform Audience Sharing]** gespeichert. |
| 3 | [!UICONTROL Integration Code] | Der Integrations-Code entspricht der Segment-ID in Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | Der Eigenschaftsausdruck ist `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Ein automatisch erstelltes Segment, das diese Eigenschaft als Komposition verwendet. |

{style="table-layout:auto"}

### Segmente {#aep-segments-as-aam-segments}

Audience Manager erstellt automatisch einen Segmentordner mit dem Namen **Experience Platform** Segmente in Ihrem Segmentspeicher.

![Screenshot des Dashboards](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Ein Beispiel für ein Segment, das automatisch aus einem Experience Platform-Segment erstellt wurde, finden Sie im folgenden Screenshot:

![Screenshot des Segments](/help/using/integration/integration-aep/assets/aep-segment.png)

| Artikelnummer | Name | Beschreibung |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | Der Integrations-Code entspricht der Segment-ID in Experience Platform. |
| 2 | [!UICONTROL Data Source] | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus dem Experience Platform von Segmenten erstellt werden, werden im **[!DNL Adobe Experience Platform Audience Sharing]** gespeichert. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** gibt an, dass automatisch erstellte Segmente der in Experience Platform eingerichteten Zusammenführungsrichtlinie entsprechen. |
| 4 | [!UICONTROL Segment Rule] | Das Segment besteht aus der Eigenschaft , die im Abschnitt „Eigenschaften[ beschrieben ](#aep-segments-as-aam-traits). |

{style="table-layout:auto"}

## Unterstützung der Audience Manager-Datenexportsteuerung in Experience Platform {#aam-data-export-control-in-aep}

Um die Einhaltung der Datennutzungsrichtlinien beim Experience Platform durchzusetzen, müssen alle entsprechenden Datensätze und Felder mit geeigneten [Datennutzungskennzeichnungen) ](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=de) werden. Darüber hinaus müssen [Datennutzungsrichtlinien](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=de) für bestimmte Marketing-Aktionen für diese Kennzeichnungen aktiviert sein, wie im [DULE-Framework (Data Usage Labeling and Enforcement](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html#dule-framework) beschrieben.

Im Prozess der Zielgruppenfreigabe zwischen Audience Manager und Experience Platform werden alle Datenexportsteuerelemente, die auf Audience Manager angewendet wurden, in entsprechende Beschriftungen und Marketing-Aktionen übersetzt, die von Experience Platform Data Governance erkannt werden, und umgekehrt.

>[!NOTE]
>
>Weitere allgemeine Informationen zu Datenexportsteuerelementen finden Sie in der [Dokumentation zu Datenexportsteuerelementen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html).
>
>Dieses Dokument bietet eine Referenz dazu, wie bestimmte Audience Manager-Datenexportsteuerelemente den Datennutzungsbeschriftungen und Marketing-Aktionen in Platform zugeordnet sind.

### Steuerelemente für den Datenexport in Datennutzungskennzeichnungen

In der folgenden Tabelle ist beschrieben, wie bestimmte Datenexportsteuerelemente den erkannten Datennutzungsbeschriftungen zugeordnet sind:

| Datenexportsteuerung | Datennutzungsbezeichnung |
| --- | --- |
| Kann nicht mit persönlich identifizierbaren Informationen verwendet werden | C3: Daten können nicht mit direkt identifizierbaren Informationen kombiniert oder anderweitig verwendet werden |
| Kann nicht für Offsite-Anzeigen-Targeting verwendet werden | C5: Daten können nicht für interessenbasiertes, Site-übergreifendes Targeting von Inhalten oder Anzeigen verwendet werden |
| Kann nicht für das Anzeigen-Targeting vor Ort verwendet werden | C6: Daten können nicht für das Targeting von Anzeigen auf der Site verwendet werden |
| Kann nicht für die Onsite-Personalisierung verwendet werden | C7: Daten können nicht für das Targeting von Inhalten auf der Site verwendet werden |

{style="table-layout:auto"}

### Steuerelemente für den Datenexport in Marketing-Aktionen

In der folgenden Tabelle ist aufgeführt, wie bestimmte Datenexportbeschriftungen den erkannten Marketing-Aktionen zugeordnet sind:

| Titel des Datenexports | Marketing-Aktion |
| --- | --- |
| Dieses Ziel kann eine Kombination mit personenbezogenen Daten (PII) ermöglichen | Kombination mit PII |
| Dieses Ziel kann für das Offsite-Anzeigen-Targeting verwendet werden | Site-übergreifendes Targeting |
| Dieses Ziel kann für das Targeting von Anzeigen auf der Site verwendet werden | Advertising vor Ort |
| Dieses Ziel kann für die Personalisierung von Anzeigen auf der Site verwendet werden | Personalization vor Ort |

{style="table-layout:auto"}

## Unterschiede bei der Segmentpopulation zwischen Audience Manager und Experience Platform {#aep-aam-segment-population-differences}

Die Anzahl der Segmentpopulationen kann je nach Audience Manager- und Experience Platform-Segment variieren. Während Segmentnummern für ähnliche oder identische Zielgruppen nahe liegen sollten, können Unterschiede in der Population auf die unten aufgeführten Faktoren zurückzuführen sein.

### Segmentauswertung im Experience Platform

Audience Manager aktualisiert die Berichtszahlen in der Benutzeroberfläche einmal täglich. Der Zeitpunkt dieser Aktualisierung entspricht selten dem Zeitpunkt der Segmentauswertung im Experience Platform.

### Unterschiede zwischen Profilzusammenführungsregeln und Zusammenführungsrichtlinien

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) in Audience Manager und [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html) in Experience Platform funktionieren unterschiedlich, und das verwendete Identitätsdiagramm ist unterschiedlich. Aus diesem Grund werden einige Unterschiede zwischen den Segmentpopulationen erwartet.

>[!NOTE]
>
> Bei der Freigabe von Segmenten von Experience Platform für Audience Manager hat Ihre Platform[Organisation (standardmäßige Zusammenführungsrichtlinie](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en#default-merge-policy) Vorrang vor der [Zusammenführungsrichtlinie, die vom Segment verwendet wird](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#merge-policies), die für Audience Manager freigegeben wurde. Wenn beispielsweise die Zusammenführungsrichtlinie des freigegebenen Segments eine [ID-Zuordnung](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=en#configure) zulässt, die standardmäßige Zusammenführungsrichtlinie des Unternehmens jedoch nicht, kann dies zu Populationsunterschieden zwischen Platform und Audience Manager führen.

### Segmentzusammensetzung in Experience Platform

Die Integration zwischen Adobe Experience Platform und Audience Manager nutzt eine Reihe von [ (Identity-](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#identity-types)) für alle Kunden: ECID, IDFA, GAID, Hash-E-Mail-Adressen (EMAIL_LC_SHA256) und AdCloud-ID. Wenn Ihre Experience Platform-Segmente eines dieser Segmente als primäre Identität für die qualifizierten Profile verwenden, werden die Profile in Audience Manager-Eigenschaften und -Segmenten gezählt.

>[!NOTE]
>
> Zielgruppen im Experience Platform mit Identitäten, die von Roh-E-Mails abgeleitet wurden, werden nie im Audience Manager angezeigt.

Hätten Sie beispielsweise ein Experience Platform-Segment „Alle meine Kunden“ und die qualifizierten Profile wären CRM-IDs, ECID, IDFA, unformatierte und gehashte E-Mail-Adressen, würde das entsprechende Segment im Audience Manager nur Profile enthalten, die von ECID-, IDFA- und gehashten E-Mail-Adressen abgeleitet wurden. Die Segmentpopulation im Audience Manager wäre kleiner als die im Experience Platform.

![Segmentfreigabe von Experience Platform nach Audience Manager - Segmentzusammensetzung](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Segmentierungs-Service - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform Segment Builder-Benutzerhandbuch](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

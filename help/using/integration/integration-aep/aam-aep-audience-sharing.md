---
description: Erfahren Sie, wie Sie die Datenfreigabe aktivieren und wie Zielgruppen zwischen Audience Manager und Adobe Experience Platform freigegeben werden
solution: Audience Manager
title: Segmentfreigabe von Experience Platform mit Audience Manager und anderen Experience Cloud-Lösungen
keywords: AEP-Zielgruppenfreigabe, AEP-Segmente, Platform-Segmente, Segmentfreigabe, Zielgruppenfreigabe, Segmentfreigabe in AAM AEP
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 1%

---

# Segmentfreigabe von Experience Platform mit Audience Manager und anderen Experience Cloud-Lösungen

## Überblick {#overview}

Mit der Funktion zur Freigabe von Audiences zwischen Audience Manager und Adobe Experience Platform können Sie Ihre Audience Manager-Eigenschaften und -Segmente für Adobe Experience Platform und Experience Platform für Audience Manager freigeben.

Sie benötigen das [[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=de) und das [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=de)-Ziel in Experience Platform, um die Freigabe von Zielgruppen zwischen Audience Manager und Adobe Experience Platform zu aktivieren.

Sie können Audience Manager-Eigenschaften und -Segmente in Experience Platform verwenden, um Ihren Kundenprofilen Audience Manager-Daten hinzuzufügen und vom Experience Platform-Segmentierungs[Service zu &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=de).

In Audience Manager können Sie Experience Platform-Segmente für Anwendungsfälle der Data Management-Plattform verwenden, z. B.:

* Fügen Sie [&#x200B; Segmente &#x200B;](/help/using/overview/data-types-collected.md#third-party-data) Drittanbieterdaten hinzu.
* [Algorithmische Modellierung](/help/using/features/algorithmic-models/understanding-models.md);
* Aktivieren Sie Ihre Segmente für Ziele, die noch nicht im Experience Platform-Zielkatalog unterstützt [&#128279;](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html?lang=de).

Darüber hinaus werden Ihre Experience Platform-Segmente über [Core Services“ für andere Experience Cloud-Lösungen &#x200B;](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html?lang=de).

>[!IMPORTANT]
>
> * Sie benötigen eine Audience Manager-Lizenz, um die oben genannten Anwendungsfälle der Data Management-Plattform zu aktivieren.
> * Sie *keine Audience Manager* Lizenz benötigen, um Experience Platform-Segmente über die Integration der zentralen Services mit Adobe Advertising Cloud, Adobe Target, Marketo und anderen Experience Cloud-Lösungen zu teilen.

In der folgenden Tabelle finden Sie einen Überblick über Anwendungsfälle für die Freigabe von Zielgruppen:

| **Nutzungsszenario** | **Adobe Experience Platform** | **Audience Manager** | **Zentrale Dienste** |
|---------|----------|---------|---------|
| **Audience Sharing** | <ul><li>Anreichern von Kundenprofilen mit Audience Manager-Daten</li><li>Verwenden von Audience Manager-Daten in der Experience Platform-Segmentierung</li></ul> | <ul><li>Hinzufügen von Drittanbieterdaten zu Segmenten</li><li>Algorithmische Modellierung</li><li>Aktivierung für zusätzliche Ziele</li></ul> | Verwenden Sie Experience Platform-Segmente in anderen Experience Cloud-Lösungen wie Adobe Target, Advertising Cloud oder Marketo. |

{style="table-layout:auto"}

## Audience Manager-Segmente und -Eigenschaften in Adobe Experience Platform {#aam-segments-traits-in-aep}

In den folgenden Abschnitten wird beschrieben, wie Sie die Datenfreigabe von Audience Manager an Experience Platform aktivieren und wie Sie Audience Manager-Eigenschaften und -Segmente in Experience Platform verwenden.

### Datenfreigabe von Audience Manager an Experience Platform aktivieren {#enable-aam-to-aep-data}

Um Segmente und Merkmale von Audience Manager an Experience Platform zu senden, müssen Sie den Audience Manager-Quell-Connector im Experience Platform-Quellkatalog einrichten. Dies ist ein Self-Service-Workflow, der keine Beteiligung der Adobe-Kundenunterstützung oder der Technik-Teams erfordert. Informationen zum Einrichten des Audience Manager-Quell-Connectors finden Sie unter:

* [Audience Manager-Quelle](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=de)
* [Erstellen einer Adobe Audience Manager-Quellverbindung über die Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=de)

>[!IMPORTANT]
>
>Adobe empfiehlt Kunden, die Verbindung zu konfigurieren, ohne die **[!UICONTROL Select all segments]**- und **[!UICONTROL Select all traits]** wie unten dargestellt auszuwählen. Die Aufnahme umfangreicher Audience Manager-Segmentpopulationen hat einen direkten Einfluss auf Ihre Gesamtprofilanzahl, wenn Sie zum ersten Mal ein Audience Manager-Segment mithilfe der Audience Manager-Quelle an Platform senden. Das bedeutet, dass die Auswahl aller Segmente möglicherweise zu einer Profilanzahl führt, die über Ihrer Lizenznutzungsberechtigung liegt.
>
>![Screenshot mit den Optionen Alle Segmente auswählen und Alle Eigenschaften auswählen , die im Workflow für die Verbindung mit dem Audience Manager-Quell-Connector nicht aktiviert sind.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Verwenden von Audience Manager-Eigenschaften und -Segmenten in Experience Platform {#use-aam-data-in-aep}

Nachdem Sie den Audience Manager-Quell-Connector zum Importieren von Eigenschaften und Segmenten aus Audience Manager eingerichtet haben, werden Ihre Audience Manager-Daten in Experience Platform **Zielgruppen** im Segment-Workflow angezeigt. Weitere Informationen zu Ihren Audience Manager-Segmenten und -Eigenschaften in Experience Platform finden Sie unter:

* [Segmentierungs-Service - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=de#audiences)
* [Benutzerhandbuch zu Experience Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=de#audiences)

## Adobe Experience Platform-Segmente in Audience Manager {#aep-segments-in-aam}

In den folgenden Abschnitten wird beschrieben, wie Sie die Datenfreigabe von Experience Platform an Audience Manager aktivieren und wie Sie Experience Platform-Segmente in Audience Manager verwenden.

### Datenfreigabe von Experience Platform an Audience Manager aktivieren {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> In diesem Abschnitt wird die veraltete Segmentfreigabeintegration von Experience Platform in Audience Manager beschrieben. Sie können diese Integration jetzt ohne Unterstützung der Adobe-Kundenbetreuer einrichten. Weitere Informationen finden Sie in der Zieldokumentation zu &lbrace;0[&#x200B; Experience Cloud Audiences.](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html?lang=de)

>[!NOTE]
>
> Wenden Sie sich an Ihren Adobe Customer Success Manager oder die Kundenunterstützung, um den Zugriff auf diese Funktion zu entsperren.

Um Segmente von Experience Platform an Audience Manager zu senden, müssen Sie sich entweder an die Kundenunterstützung oder Ihren Customer Success Manager wenden. Die Teams der Kundenunterstützung und des Support-Managements müssen ein Ticket erstellen (siehe Vorlagenticket AAM-52354), um die Verbindung von Platform mit Audience Manager zu aktivieren.

Stellen Sie sicher, dass Sie Pläne für die Daten von Platform an Audience Manager freigeben, um sicherzustellen, dass die Verbindung korrekt eingerichtet ist. Wenn beispielsweise regionale Daten für Segmente freigegeben werden sollen, die an Adobe Target gesendet werden, müssen diese Informationen im Ticket kommuniziert werden. Die Datenfreigabeverbindung von Experience Platform zu Audience Manager wird innerhalb von sechs Werktagen nach der Anfrage eingerichtet.

### Verwenden von Experience Platform-Segmenten in Audience Manager {#use-aep-data-in-aam}

Segmente, die Sie in Experience Platform erstellen, werden in Ihrer Audience Manager-Benutzeroberfläche als Signale, Eigenschaften und Segmente mit den folgenden Kompositionsregeln angezeigt:

* Signal: Für jedes Experience Platform-Segment sollten Signale im `segID = segment ID` angezeigt werden.
* Eigenschaft : Die Eigenschaftsregel ist die ID des Experience Platform-Segments.
* Segment: Das Segment besteht aus der oben beschriebenen Eigenschaft.

### Signale {#aep-segments-as-aam-signals}

Wählen Sie **[!UICONTROL Audience Data > Signals > General Online Data]** und suchen Sie nach `SegId`, um Signale zu finden, die von Experience Platform eingehen. Sie können diesen Bildschirm zum Debugging verwenden, um zu überprüfen, ob die Integration zwischen Experience Platform und Audience Manager korrekt eingerichtet wurde.

![Siehe Experience Platform-Signale in Audience Manager im Signale-Dashboard](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Eigenschaften {#aep-segments-as-aam-traits}

Audience Manager erstellt in Ihrem Eigenschaftsspeicher automatisch einen Eigenschaftsordner mit **Namen** Experience Platform-Eigenschaften.

![Eigenschaften aus dem Experience Platform-Dashboard](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Sie können automatisch erstellte Eigenschaften in Segmenten zusammen mit anderen Eigenschaften verwenden. Sie können beispielsweise Eigenschaften, die aus Experience Platform-Segmenten erstellt wurden, mit Eigenschaften von Drittanbietern mischen, die über die [Audience Marketplace erworben &#x200B;](/help/using/features/audience-marketplace/audience-marketplace.md).

Ein Beispiel für eine Eigenschaft, die automatisch aus einem Experience Platform-Segment erstellt wurde, finden Sie im folgenden Screenshot:

![Eigenschaft aus Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Artikelnummer | Name | Beschreibung |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Aus Experience Platform-Segmenten erstellte Eigenschaften werden in Audience Manager als integrierte Eigenschaften erstellt. |
| 2 | [!UICONTROL Data Source] | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus Experience Platform-Segmenten erstellt werden, werden im **[!UICONTROL Adobe Experience Platform Audience Sharing]** gespeichert. |
| 3 | [!UICONTROL Integration Code] | Der Integrations-Code entspricht der Segment-ID in Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | Der Eigenschaftsausdruck ist `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Ein automatisch erstelltes Segment, das diese Eigenschaft als Komposition verwendet. |

{style="table-layout:auto"}

### Segmente {#aep-segments-as-aam-segments}

Audience Manager erstellt automatisch einen Segmentordner mit dem Namen **Experience Platform** in Ihrem Segmentspeicher.

![Screenshot des Dashboards](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Ein Beispiel für ein Segment, das automatisch aus einem Experience Platform-Segment erstellt wurde, finden Sie im folgenden Screenshot:

![Screenshot des Segments](/help/using/integration/integration-aep/assets/aep-segment.png)

| Artikelnummer | Name | Beschreibung |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | Der Integrations-Code entspricht der Segment-ID in Experience Platform. |
| 2 | [!UICONTROL Data Source] | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus Experience Platform-Segmenten erstellt werden, werden im **[!DNL Adobe Experience Platform Audience Sharing]** gespeichert. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** gibt an, dass automatisch erstellte Segmente der in Experience Platform eingerichteten Zusammenführungsrichtlinie entsprechen. |
| 4 | [!UICONTROL Segment Rule] | Das Segment besteht aus der Eigenschaft , die im Abschnitt „Eigenschaften[&#x200B; beschrieben &#x200B;](#aep-segments-as-aam-traits). |

{style="table-layout:auto"}

## Unterstützung der Audience Manager-Datenexportsteuerung in Experience Platform {#aam-data-export-control-in-aep}

Um die Einhaltung der Datennutzungsrichtlinien in Experience Platform durchzusetzen, müssen alle entsprechenden Datensätze und Felder mit entsprechenden [Datennutzungskennzeichnungen) &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=de) werden. Darüber hinaus müssen [Datennutzungsrichtlinien](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=de) für bestimmte Marketing-Aktionen für diese Kennzeichnungen aktiviert sein, wie im [DULE-Framework (Data Usage Labeling and Enforcement](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html?lang=de#dule-framework) beschrieben.

Im Prozess der Zielgruppenfreigabe zwischen Audience Manager und Experience Platform werden alle Datenexportsteuerelemente, die auf Audience Manager-Segmente angewendet wurden, in entsprechende Beschriftungen und Marketing-Aktionen übersetzt, die von Experience Platform Data Governance erkannt werden, und umgekehrt.

>[!NOTE]
>
>Weitere allgemeine Informationen zu Datenexportsteuerelementen finden Sie in der [Dokumentation zu Datenexportsteuerelementen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=de).
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

Die Anzahl der Segmentpopulationen kann zwischen Ihren Segmenten in Audience Manager und Experience Platform variieren. Während Segmentnummern für ähnliche oder identische Zielgruppen nahe liegen sollten, können Unterschiede in der Population auf die unten aufgeführten Faktoren zurückzuführen sein.

### Segmentauswertung in Experience Platform

Audience Manager aktualisiert die Berichtszahlen in der Benutzeroberfläche einmal täglich. Der Zeitpunkt dieser Aktualisierung stimmt nur selten mit dem Zeitpunkt der Segmentauswertung in Experience Platform überein.

### Unterschiede zwischen Profilzusammenführungsregeln und Zusammenführungsrichtlinien

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) in Audience Manager und [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html?lang=de) in Experience Platform funktionieren unterschiedlich, und das verwendete Identitätsdiagramm variiert je nach Konfiguration. Aus diesem Grund werden einige Unterschiede zwischen den Segmentpopulationen erwartet.

>[!NOTE]
>
> Bei der Freigabe von Segmenten von Experience Platform für Audience Manager hat Ihre Platform[Organisation (standardmäßige Zusammenführungsrichtlinie](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=de#default-merge-policy) Vorrang vor der [Zusammenführungsrichtlinie, die vom Segment verwendet wird](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=de#merge-policies), das für Audience Manager freigegeben wurde. Wenn beispielsweise die Zusammenführungsrichtlinie des freigegebenen Segments eine [ID-Zuordnung](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=de#configure) zulässt, die standardmäßige Zusammenführungsrichtlinie des Unternehmens jedoch nicht, kann dies zu Populationsunterschieden zwischen Platform und Audience Manager führen.

### Segmentkomposition in Experience Platform

Die Integration zwischen Adobe Experience Platform und Audience Manager nutzt eine Reihe von [&#x200B; (Identity-](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html?lang=de#identity-types)) für alle Kunden: ECID, IDFA, GAID, Hash-E-Mail-Adressen (EMAIL_LC_SHA256) und AdCloud-ID. Wenn Ihre Experience Platform-Segmente eine dieser Eigenschaften als primäre Identität für die qualifizierten Profile verwenden, werden die Profile in Audience Manager-Eigenschaften und -Segmenten gezählt.

>[!NOTE]
>
> Zielgruppen in Experience Platform mit Identitäten, die von unbearbeiteten E-Mails abgeleitet wurden, werden in Audience Manager nie angezeigt.

Wenn Sie beispielsweise ein Experience Platform-Segment „Alle meine Kunden“ hätten und die qualifizierten Profile CRM-IDs, ECID, IDFA, unformatierte und gehashte E-Mail-Adressen wären, würde das entsprechende Segment in Audience Manager nur Profile enthalten, die von ECID-, IDFA- und Hash-E-Mail-Adressen abgeleitet wurden. Die Segmentpopulation in Audience Manager wäre kleiner als die in Experience Platform.

![Segmentfreigabe von Experience Platform zu Audience Manager - Segmentzusammensetzung](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Segmentierungs-Service - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=de#audiences)
>* [Benutzerhandbuch zu Experience Platform Segment Builder](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html?lang=de#audiences)
>* [Audience Manager-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html?lang=de)

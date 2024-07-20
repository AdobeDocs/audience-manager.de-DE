---
description: Erfahren Sie, wie Sie die Datenfreigabe aktivieren und wie Zielgruppen zwischen Audience Manager und Adobe Experience Platform freigegeben werden.
solution: Audience Manager
title: Experience Platform der Segmentfreigabe mit Audience Manager und anderen Experience Cloud-Lösungen
keywords: Freigabe von AEP-Zielgruppen, AEP-Segmente, Platform-Segmente, Segmentfreigabe, Zielgruppenfreigabe, Freigabe von Segmenten AAM AEP-Segmentfreigabe
feature: Experience Platform Integration
exl-id: 46ad306f-3e87-4731-8ba0-cfafefa616fc
source-git-commit: d21d0574ee0338dbd5e11c60e0d64042182aa18b
workflow-type: tm+mt
source-wordcount: '1799'
ht-degree: 1%

---

# Experience Platform der Segmentfreigabe mit Audience Manager und anderen Experience Cloud-Lösungen

## Überblick {#overview}

Mit der Zielgruppenfreigabe zwischen Audience Manager und Adobe Experience Platform können Sie Ihre Audience Manager-Eigenschaften und -Segmente für Adobe Experience Platform und Experience Platform-Segmente für Audience Manager freigeben.

Sie benötigen das Ziel [[!DNL Audience Manager source connector]](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html) und das Ziel [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html) in Experience Platform, um die Zielgruppenfreigabe zwischen Audience Manager und Adobe Experience Platform zu aktivieren.

Sie können Audience Manager-Eigenschaften und -Segmente in Experience Platform verwenden, um Ihren Kundenprofilen Audience Manager-Daten hinzuzufügen und vom Experience Platform [Segmentierungsdienst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=en) zu profitieren.

In Audience Manager können Sie Experience Platform-Segmente für Anwendungsfälle von Data Management Platform verwenden, z. B.:
* Fügen Sie [Drittanbieterdaten](/help/using/overview/data-types-collected.md#third-party-data) zu Ihren Segmenten hinzu.
* [Algorithmische Modellierung](/help/using/features/algorithmic-models/understanding-models.md);
* Aktivieren Sie Ihre Segmente für Ziele, die noch nicht im Experience Platform [Zielkatalog](https://experienceleague.adobe.com/docs/experience-platform/rtcdp/destinations/destinations-cat/destinations-catalog.html) unterstützt werden.

Darüber hinaus werden Ihre Experience Platform-Segmente über [Core Services](https://experienceleague.adobe.com/docs/core-services/interface/experience-cloud.html) für andere Experience Cloud-Lösungen freigegeben.

>[!IMPORTANT]
>
> * Sie benötigen eine Audience Manager-Lizenz, um die oben genannten Anwendungsfälle der Data Management Platform zu aktivieren.
> * Sie benötigen *keine Audience Manager-Lizenz, um Experience Platform-Segmente über die Core Services-Integration für Adobe Advertising Cloud, Adobe Target, Marketo und andere Experience Cloud-Lösungen freizugeben.*

Eine Übersicht der Anwendungsfälle für die Zielgruppenfreigabe finden Sie in der unten stehenden Tabelle:

| **Nutzungsszenario** | **Adobe Experience Platform** | **Audience Manager** | **Zentrale Dienste** |
|---------|----------|---------|---------|
| **Zielgruppenfreigabe** | <ul><li>Kundenprofile mit Audience Manager-Daten anreichern</li><li>Audience Manager-Daten in Experience Platform-Segmentierung verwenden</li></ul> | <ul><li>Hinzufügen von Drittanbieterdaten zu Segmenten</li><li>Algorithmische Modellierung</li><li>Aktivierung an zusätzlichen Zielen</li></ul> | Verwenden Sie Experience Platform-Segmente in anderen Experience Cloud-Lösungen wie Adobe Target, Advertising Cloud oder Marketo. |

{style="table-layout:auto"}

## Audience Manager-Segmente und -Eigenschaften in Adobe Experience Platform {#aam-segments-traits-in-aep}

In den folgenden Abschnitten wird beschrieben, wie Sie die Datenfreigabe vom Audience Manager zum Experience Platform aktivieren und Audience Manager-Eigenschaften und -Segmente im Experience Platform verwenden.

### Datenfreigabe von Audience Manager zu Experience Platform aktivieren {#enable-aam-to-aep-data}

Um Segmente und Eigenschaften von Audience Manager an Experience Platform zu senden, müssen Sie den Quell-Connector für Audience Manager im Experience Platform-Quellenkatalog einrichten. Dies ist ein Self-Service-Workflow, der keine Beteiligung der Adobe-Kundenunterstützung oder von Technikerteams erfordert. Lesen Sie zum Einrichten des Quell-Connectors für den Audience Manager Folgendes:

* [Audience Manager source](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)
* [Erstellen einer Adobe Audience Manager-Quellverbindung in der Benutzeroberfläche](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/audience-manager.html?lang=en)

>[!IMPORTANT]
>
>Adobe ermutigt Kunden, die Verbindung zu konfigurieren, ohne die Optionen **[!UICONTROL Select all segments]** und **[!UICONTROL Select all traits]** wie unten dargestellt auszuwählen. Die Erfassung umfangreicher Audience Manager-Segmentpopulationen hat einen direkten Einfluss auf Ihre Gesamtprofilanzahl, wenn Sie zum ersten Mal ein Audience Manager-Segment mit der Audience Manager-Quelle an Platform senden. Das bedeutet, dass die Auswahl aller Segmente potenziell zu einer Profilanzahl führen kann, die über Ihrer Lizenznutzungsberechtigung liegt.
>
>![Screenshot mit den Optionen Alle Segmente auswählen und Alle Eigenschaften auswählen deaktiviert im Workflow, um eine Verbindung zum Quell-Connector des Audience Managers herzustellen.](/help/using/integration/integration-aep/assets/select-all-segments-traits-unchecked.png)

### Verwenden von Audience Manager-Eigenschaften und -Segmenten in Experience Platform {#use-aam-data-in-aep}

Nachdem Sie den Audience Manager-Quell-Connector eingerichtet haben, um Eigenschaften und Segmente aus Audience Manager zu importieren, werden Ihre Audience Manager-Daten im Segmentarbeitsablauf unter Experience Platform als **Zielgruppen** angezeigt. Weitere Informationen zu Ihren Audience Manager-Segmenten und -Eigenschaften in Experience Platform finden Sie unter:

* [Segmentation Service - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
* [Experience Platform Segment Builder-Benutzerhandbuch](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)

## Adobe Experience Platform-Segmente in Audience Manager {#aep-segments-in-aam}

In den folgenden Abschnitten wird beschrieben, wie Sie die Datenfreigabe von Experience Platform an Audience Manager aktivieren und Experience Platform-Segmente in Audience Manager verwenden.

### Datenfreigabe von Experience Platform an Audience Manager aktivieren {#enable-aep-to-aam-data}

>[!IMPORTANT]
>
> In diesem Abschnitt wird die Integration der Segmentfreigabe von Experience Platform in Audience Manager beschrieben. Sie können diese Integration jetzt ohne Unterstützung von Adobe-Kundenvertretern einrichten. Weitere Informationen finden Sie in der Zieldokumentation für [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/adobe/experience-cloud-audiences.html) .

>[!NOTE]
>
> Wenden Sie sich an Ihren Adobe Customer Success Manager oder an die Kundenunterstützung, um den Zugriff auf diese Funktion zu entsperren.

Um Segmente von Experience Platform an Audience Manager zu senden, müssen Sie sich entweder an die Kundenunterstützung oder Ihren Customer Success Manager wenden. Die Teams der Kundenunterstützung und des Kundensupport müssen ein Ticket (siehe Vorlagenticket AAM-52354) einreichen, um die Verbindung von Platform zu Audience Manager zu ermöglichen.

Stellen Sie sicher, dass Sie Pläne für die Daten freigeben, die von Platform an Audience Manager gesendet werden, um sicherzustellen, dass die Verbindung ordnungsgemäß eingerichtet ist. Wenn beispielsweise regionale Daten für an Adobe Target gesendete Segmente freigegeben werden sollen, müssen diese Informationen im Ticket übermittelt werden. Die Datenfreigabe-Verbindung zwischen Experience Platform und Audience Manager wird innerhalb von sechs Werktagen nach der Übermittlung der Anfrage eingerichtet.

### Verwenden von Experience Platform-Segmenten in Audience Manager {#use-aep-data-in-aam}

Segmente, die Sie in Experience Platform erstellen, werden in Ihrer Audience Manager-Oberfläche als Signale, Eigenschaften und Segmente mit den folgenden Kompositionsregeln angezeigt:

* Signal: Für jedes Experience Platform-Segment sollten Signale im Format `segID = segment ID` angezeigt werden.
* Eigenschaft: Die Eigenschaftsregel ist die ID des Experience Platform-Segments.
* Segment: Das Segment besteht aus der oben beschriebenen Eigenschaft.

### Signale {#aep-segments-as-aam-signals}

Wählen Sie **[!UICONTROL Audience Data > Signals > General Online Data]** und suchen Sie nach `SegId` , um Signale zu finden, die von Experience Platform kommen. Sie können diesen Bildschirm zu Debugging-Zwecken verwenden, um zu überprüfen, ob die Integration zwischen Experience Platform und Audience Manager korrekt eingerichtet wurde.

![Siehe Experience Platform-Signale im Audience Manager im Signale-Dashboard](/help/using/integration/integration-aep/assets/aep-signals-in-aam.png)

### Eigenschaften {#aep-segments-as-aam-traits}

Audience Manager erstellt automatisch einen Eigenschaftsordner mit dem Namen **Experience Platform-Eigenschaften** in Ihrem Eigenschaftsspeicher.

![Eigenschaften vom Experience Platform-Dashboard](/help/using/integration/integration-aep/assets/aep-traits-dashboard.png)

Sie können automatisch erstellte Eigenschaften in Segmenten zusammen mit anderen Eigenschaften verwenden. Sie können beispielsweise Eigenschaften, die aus Experience Platform-Segmenten erstellt wurden, mit Eigenschaften von Drittanbietern kombinieren, die über die [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md) erfasst wurden.

Ein Beispiel für eine Eigenschaft, die automatisch aus einem Experience Platform-Segment erstellt wurde, finden Sie im folgenden Screenshot:

![Eigenschaft von Experience Platform](/help/using/integration/integration-aep/assets/aep-trait.png)


| Artikelnummer | Name | Beschreibung |
|---------|----------|---------|
| 1 | [!UICONTROL Trait Type] | Eigenschaften, die aus Experience Platform-Segmenten erstellt wurden, werden als integrierte Eigenschaften in Audience Manager erstellt. |
| 2 | [!UICONTROL Data Source] | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus Experience Platform-Segmenten erstellt werden, werden in der Datenquelle **[!UICONTROL Adobe Experience Platform Audience Sharing]** gespeichert. |
| 3 | [!UICONTROL Integration Code] | Der Integrationscode entspricht der Segment-ID in Experience Platform. |
| 4 | [!UICONTROL Trait Expression] | Der Eigenschaftsausdruck ist `segID = segment ID in Experience Platform`. |
| 5 | [!UICONTROL Segments with this Trait] | Ein automatisch erstelltes Segment, das diese Eigenschaft als Komposition verwendet. |

{style="table-layout:auto"}

### Segmente {#aep-segments-as-aam-segments}

Audience Manager erstellt automatisch einen Segmentordner mit dem Namen **Experience Platform-Segmente** in Ihrem Segmentspeicher.

![Screenshot des Dashboards](/help/using/integration/integration-aep/assets/aep-segments-dashboard.png)

Ein Beispiel für ein Segment, das automatisch aus einem Experience Platform-Segment erstellt wurde, finden Sie im folgenden Screenshot:

![Screenshot des Segments](/help/using/integration/integration-aep/assets/aep-segment.png)

| Artikelnummer | Name | Beschreibung |
|---------|----------|---------|
| 1 | [!UICONTROL Integration Code] | Der Integrationscode entspricht der Segment-ID in Experience Platform. |
| 2 | [!UICONTROL Data Source] | Automatisch erstellt. Alle Eigenschaften und Segmente, die automatisch aus Experience Platform-Segmenten erstellt werden, werden in der Datenquelle **[!DNL Adobe Experience Platform Audience Sharing]** gespeichert. |
| 3 | [!UICONTROL Profile Merge Rule] | **[!UICONTROL External Merge Policy]** gibt an, dass automatisch erstellte Segmente der in Experience Platform festgelegten Zusammenführungsrichtlinie entsprechen. |
| 4 | [!UICONTROL Segment Rule] | Das Segment besteht aus der Eigenschaft, die im Abschnitt [Eigenschaften](#aep-segments-as-aam-traits) beschrieben ist. |

{style="table-layout:auto"}

## Unterstützung der Audience Manager-Datenexportkontrolle beim Experience Platform {#aam-data-export-control-in-aep}

Um die Datennutzungskonformität im Experience Platform zu erzwingen, müssen alle entsprechenden Datensätze und Felder mit entsprechenden [Datennutzungsbezeichnungen](https://experienceleague.adobe.com/docs/experience-platform/data-governance/labels/overview.html?lang=de) versehen werden. Darüber hinaus müssen [Datennutzungsrichtlinien](https://experienceleague.adobe.com/docs/experience-platform/data-governance/policies/overview.html?lang=de) für bestimmte Marketing-Aktionen für diese Beschriftungen aktiviert werden, wie im DULE-Framework (Data Usage Labeling and Enforcement)](https://experienceleague.adobe.com/docs/experience-platform/data-governance/home.html#dule-framework) beschrieben.[

Im Zielgruppenfreigabe-Prozess zwischen Audience Manager und Experience Platform werden alle Datenexportkontrollen, die auf Audience Manager-Segmente angewendet wurden, in entsprechende Beschriftungen und Marketing-Aktionen übersetzt, die von Experience Platform Data Governance erkannt werden, und umgekehrt.

>[!NOTE]
>
>Allgemeine Informationen zu Datenexportkontrollen finden Sie in der Dokumentation [Datenexportkontrollen](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html).
>
>Dieses Dokument bietet eine Referenz dazu, wie bestimmte Audience Manager-Datenexportkontrollen den Datennutzungsbezeichnungen und Marketing-Aktionen in Platform zugeordnet werden.

### Datenexportkontrollen zu Datennutzungsbezeichnungen

In der folgenden Tabelle wird erläutert, wie bestimmte Datenexportkontrollen erkannten Datennutzungsbezeichnungen zugeordnet werden:

| Datenexportkontrolle | Datennutzungsbezeichnung |
| --- | --- |
| Kann nicht mit persönlich identifizierbaren Informationen verwendet werden | C3: Daten können nicht mit direkt identifizierbaren Informationen kombiniert oder anderweitig verwendet werden |
| Kann nicht für Offsite-Anzeigen-Targeting verwendet werden | C5: Daten können nicht für interessensbasiertes, Site-übergreifendes Targeting von Inhalten oder Anzeigen verwendet werden |
| Kann nicht für Onsite-Anzeigen-Targeting verwendet werden | C6: Daten können nicht für die On-site-Anzeigensuche verwendet werden |
| Kann nicht für die Personalisierung vor Ort verwendet werden | C7: Daten können nicht für das On-site-Targeting von Inhalten verwendet werden |

{style="table-layout:auto"}

### Datenexportkontrollen für Marketing-Aktionen

In der folgenden Tabelle wird beschrieben, wie bestimmte Datenexport-Beschriftungen erkannten Marketing-Aktionen zugeordnet werden:

| Datenexportbezeichnung | Marketing-Aktion |
| --- | --- |
| Dieses Ziel kann eine Kombination mit persönlich identifizierbaren Informationen (PII) ermöglichen | Kombinieren mit PII |
| Dieses Ziel kann für Offsite-Anzeigen-Targeting verwendet werden | Site-übergreifendes Targeting |
| Dieses Ziel kann für On-site-Anzeigen-Targeting verwendet werden. | Onsite Advertising |
| Dieses Ziel kann für die On-site-Anzeigenpersonalisierung verwendet werden | Onsite Personalization |

{style="table-layout:auto"}

## Grundlegendes zu Segmentpopulationsunterschieden zwischen Audience Manager und Experience Platform {#aep-aam-segment-population-differences}

Die Segmentpopulationszahlen können zwischen Ihren Audience Manager- und Experience Platform-Segmenten variieren. Während Segmentzahlen für ähnliche oder identische Zielgruppen nahe liegen sollten, können die Unterschiede in Populationen auf die unten aufgeführten Faktoren zurückzuführen sein.

### Segmentbewertung in Experience Platform

Audience Manager aktualisiert die Berichtsnummern in der Benutzeroberfläche einmal täglich. Der Zeitpunkt dieser Aktualisierung stimmt selten mit dem Zeitpunkt der Segmentbewertung in Experience Platform überein.

### Unterschiede zwischen Profilzusammenführungsrichtlinien und Zusammenführungsrichtlinien

[[!UICONTROL Profile Merge Rules]](/help/using/features/profile-merge-rules/merge-rules-overview.md) in Audience Manager und [[!UICONTROL Merge Policies]](https://experienceleague.adobe.com/docs/experience-platform/profile/ui/merge-policies.html) in Experience Platform funktionieren unterschiedlich, und das für jede Version verwendete Identitätsdiagramm variiert. Daher werden einige Unterschiede zwischen Segmentpopulationen erwartet.

>[!NOTE]
>
> Beim Freigeben von Segmenten von Experience Platform an Audience Manager hat Ihre Platform-Organisation [standardmäßige Zusammenführungsrichtlinie](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/overview.html?lang=en#default-merge-policy) Vorrang vor der [Zusammenführungsrichtlinie, die von der für Audience Manager freigegebenen Segmentrichtlinie](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/segment-builder.html?lang=en#merge-policies) verwendet wird. Wenn die Zusammenführungsrichtlinie des freigegebenen Segments beispielsweise die [ID-Zuordnung](https://experienceleague.adobe.com/docs/experience-platform/profile/merge-policies/ui-guide.html?lang=en#configure) zulässt, die standardmäßige Zusammenführungsrichtlinie des Unternehmens dies jedoch nicht tut, kann dies zu Populationsunterschieden zwischen Platform und Audience Manager führen.

### Segmentzusammenstellung in Experience Platform

Die Integration zwischen Adobe Experience Platform und Audience Manager nutzt eine Reihe von standardmäßigen [Identitäts-Namespaces](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#identity-types) für alle Kunden: ECID, IDFA, GAID, Hash-E-Mail-Adressen (EMAIL_LC_SHA256), AdCloud ID. Wenn Ihre Experience Platform-Segmente eine dieser Eigenschaften als primäre Identität für die qualifizierten Profile verwenden, werden die Audience Manager in Eigenschaften und Segmenten gezählt.

>[!NOTE]
>
> Zielgruppen im Experience Platform mit Identitäten, die von Roh-E-Mails abgeleitet wurden, werden in Audience Manager nie angezeigt.

Wenn Sie beispielsweise über das Experience Platform-Segment &quot;Alle meine Kunden&quot;verfügen und die qualifizierten Profile CRM-IDs, ECID, IDFA, Roh- und Hash-E-Mail-Adressen sind, enthält das entsprechende Segment in Audience Manager nur Profile, die von ECID-, IDFA- und Hash-E-Mail-Adressen abgeleitet wurden. Die Segmentpopulation in Audience Manager wäre kleiner als die in Experience Platform.

![Experience Platform zum Teilen von Audience Manager-Segmenten - Segmentkomposition](assets/AEP-to-AAM-profiles.png)

<!--

If you created a data source in Audience Manager for the CRM IDs in Experience Platform, then the qualified profiles keyed off those CRM IDs would appear in Audience Manager and the segment population in Audience Manager would increase.

![AEP to AAM segment sharing - segment composition after creating a data source for CRM IDs in Audience Manager](/help/using/integration/integration-aep/assets/AEP-to-AAM-identities2.png)

-->


>[!MORELIKETHIS]
>
>* [Segmentation Service - Übersicht](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html#audiences)
>* [Experience Platform Segment Builder-Benutzerhandbuch](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html#audiences)
>* [Audience Manager-Connector](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/audience-manager.html)

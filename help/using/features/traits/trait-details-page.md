---
description: Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie Eigenschaftsname, ID, Leistungsmetriken, Ausdruck, die die Eigenschaft definieren, Segmente, zu denen sie gehört, und das Eigenschafts-Prüfprotokoll. Um diese Details anzuzeigen, gehen Sie zu "Audience-Daten"> "Eigenschaften"und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.
seo-description: Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie Eigenschaftsname, ID, Leistungsmetriken, Ausdruck, die die Eigenschaft definieren, Segmente, zu denen sie gehört, und das Eigenschafts-Prüfprotokoll. Um diese Details anzuzeigen, gehen Sie zu "Audience-Daten"> "Eigenschaften"und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.
seo-title: Detailseite einer Eigenschaft
solution: Audience Manager
title: Detailseite einer Eigenschaft
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 1%

---


# [!UICONTROL Trait] Detailseite {#trait-details-page}

Die Detailseite für eine Einzelperson [!UICONTROL trait] bietet einen Überblick über die [!UICONTROL trait] Details, wie z. B. [!UICONTROL trait] Name, ID, Leistungsmetriken, Ausdruck, die die Variable definieren [!UICONTROL trait], Segmente, zu denen sie gehört, und das [!UICONTROL trait] Prüfprotokoll. Um diese Details Ansicht, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** und klicken Sie auf den Namen des [!UICONTROL trait] gewünschten Artikels.

## [!UICONTROL Trait] Verwaltungstools {#trait-management-tools}

Oben auf der [!UICONTROL trait] Detailseite finden Sie die Tools, mit denen Sie Ihre [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: Verwenden Sie diese Option, um neue [!UICONTROL rule-based], [!UICONTROL algorithmic]oder [!UICONTROL onboarded traits]zu erstellen.
2. **[!UICONTROL Edit]**: Verwenden Sie diese Option, um die Konfiguration der aktuellen Version zu ändern [!UICONTROL trait].
3. **[!UICONTROL Delete]**: Verwenden Sie diese Option, um den aktuellen Eintrag [!UICONTROL trait] aus Ihrem Audience Manager-Konto zu entfernen.
4. **[!UICONTROL Marketplace Recommendations]**: Verwenden Sie diese Option ähnlich [!UICONTROL traits] wie die angezeigte, aus den [!UICONTROL Audience Marketplace] Datengebühren, die Sie nicht abonniert haben. Siehe [Audience Marketplace für Datenkäufer](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) , um zu erfahren, wie Sie in der Seite navigieren [!UICONTROL Marketplace] und ähnliche Eigenschaften finden.

![basic-property-information](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informationen {#basics}

Der [!UICONTROL Trait Information] Abschnitt enthält Details zu erforderlichen und optionalen Feldern, die Sie beim Erstellen der [!UICONTROL trait]Datei ausgefüllt haben. Dazu gehören Elemente wie [!UICONTROL trait] Typ, [!UICONTROL trait] ID, Beschreibung [!UICONTROL data source]und andere Metadaten. Diese Details variieren je nach [!UICONTROL trait] Typ ([!UICONTROL folder], [!UICONTROL onboarded]oder [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

Der Bericht [!UICONTROL Trait Graph] enthält Leistungsmetriken auf einen Blick für die ausgewählte Version [!UICONTROL trait]. Halten Sie den Cursor über eine Trendlinie, um weitere Daten für die ausgewählte Zeile anzuzeigen [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] stellen eine Anzahl individueller Benutzer dar, die dies über einen bestimmten Zeitraum ihrem Profil [!UICONTROL trait] hinzugefügt haben. Die [!UICONTROL Total Trait Population] gibt die Anzahl der Unique Users an, die derzeit für diese Aktion qualifiziert sind [!UICONTROL trait].

Die [!UICONTROL rule-based traits]Qualifizierung erfolgt [!UICONTROL trait] beispielsweise in Echtzeit, da Benutzer sich für eine [!UICONTROL trait] in ihrem Browser qualifizieren.

Die [!UICONTROL onboarded traits]Qualifizierung erfolgt [!UICONTROL trait] beispielsweise nach der Verarbeitung einer eingehenden Datei, d. h., die eingehende Datei wird in den Audience Manager [](../../faq/faq-inbound-data-ingestion.md) eingespeist und dann erfolgt die [!UICONTROL trait] Qualifizierung.

Die [!UICONTROL Trait Graph] zeigt die folgenden Informationen an:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: Wählen Sie diese Option aus, um die Ergebnisse für [!UICONTROL traits] die Datenerfassung für authentifizierte Profil anzuzeigen. Wenn Sie diese Option auswählen, werden nur Daten im [!UICONTROL Cross-Device ID] Bericht angezeigt, und es werden keine Daten im [!UICONTROL Device ID] Bericht angezeigt.
   * **[!UICONTROL Device ID]**: Wählen Sie diese Option aus, um die Ergebnisse für [!UICONTROL traits] die Datenerfassung für Geräte-Profil anzuzeigen. Wenn Sie diese Option auswählen, werden nur Daten im [!UICONTROL Device ID] Bericht angezeigt, und es werden keine Daten im [!UICONTROL Cross-Device ID] Bericht angezeigt.

      ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Anzahl der Unique Users, die dies über einen bestimmten Zeitraum zu ihrem Profil hinzugefügt [!UICONTROL trait] haben.
* **[!UICONTROL Total Trait Population]**: Die Anzahl der Unique Users, die derzeit für diese Einstellung qualifiziert sind [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: Die ersten drei Einträge zeigen die drei Top [!UICONTROL cross-device data sources] mit der höchsten Bevölkerungszahl, die sich für die [!UICONTROL trait]in absteigender Reihenfolge qualifiziert haben. Der vierte Eintrag zeigt die Summe aller anderen [!DNL DPUUIDs] ([!DNL CRM IDs]), die sich für die [!UICONTROL trait], von den [!UICONTROL cross-device data sources] , die nicht in den oberen drei. Dieser Bericht wird nur angezeigt, wenn Sie oben rechts auf der Seite [!UICONTROL Cross-device ID] im [!UICONTROL Show Results By] Dropdownmenü auswählen. Die standardmäßige Dropdown-Option ist [!UICONTROL Device ID]die, bei der dieser Bericht nicht angezeigt wird.

   ![trait-graph](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager zeigt den [!UICONTROL Identity Type Breakdown] Bericht nur an, wenn Sie über [!UICONTROL cross-device] IDs verfügen, die für den Bericht qualifiziert sind [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Ausdruck {#trait-expression}

Der [!UICONTROL Trait Expression] Abschnitt zeigt Ihnen, welche Kriterien Benutzer erfüllen müssen, um sich für die [!UICONTROL trait]Teilnahme zu qualifizieren. Diese Regeln werden festgelegt, wenn Sie eine Eigenschaft [erstellen oder bearbeiten](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segmente {#trait-segments}

Im [!UICONTROL Segments with this Trait] Abschnitt werden alle Segmente Liste, zu denen die Auswahl [!UICONTROL trait] gehört. Sie können auf einen Segmentnamen klicken, um Details zu diesem Segment anzuzeigen.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Audit-/Verlaufsprotokoll {#trait-audit-history}

Für [!UICONTROL rule-based] und [!UICONTROL onboarded traits]zeigt die [!UICONTROL Trait Expression Change History] Liste die letzten 10 Änderungen an den [!UICONTROL trait] Ausdruck-Regeln an und wer sie vorgenommen hat. Wenn Sie mehr als 10 Änderungen [!UICONTROL trait] vorgenommen haben, klicken Sie auf **[!UICONTROL Export to CSV]** , um das gesamte Prüfprotokoll herunterzuladen. Das Prüfprotokoll steht nicht zur Verfügung [!UICONTROL folder] oder [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] in der [!UICONTROL By User] Spalte bedeutet, dass das Konto für diesen Benutzer gelöscht wurde.

![](assets/traitHistory.png)
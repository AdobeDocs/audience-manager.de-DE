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


# [!UICONTROL Trait] Detailseite  {#trait-details-page}

Die Detailseite für ein einzelnes [!UICONTROL trait] bietet einen Überblick über die [!UICONTROL trait]-Details, wie z. B. [!UICONTROL trait] name, ID, Performance-Metriken, Ausdruck, die das [!UICONTROL trait] definieren, Segmente, zu denen es gehört, und das [!UICONTROL trait]-Prüfprotokoll. Um diese Details Ansicht, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** und klicken Sie auf den Namen des [!UICONTROL trait], mit dem Sie arbeiten möchten.

## [!UICONTROL Trait] Verwaltungstools  {#trait-management-tools}

Am oberen Rand der Detailseite [!UICONTROL trait] befinden sich die Tools, mit denen Sie Ihre [!UICONTROL traits] verwalten können:

1. **[!UICONTROL Add New]**: Verwenden Sie diese Option, um neue  [!UICONTROL rule-based],  [!UICONTROL algorithmic]oder  [!UICONTROL onboarded traits]zu erstellen.
2. **[!UICONTROL Edit]**: Verwenden Sie diese Option, um die Konfiguration der aktuellen Version zu ändern  [!UICONTROL trait].
3. **[!UICONTROL Delete]**: Verwenden Sie diese Option, um den aktuellen Eintrag  [!UICONTROL trait] aus Ihrem Audience Manager-Konto zu entfernen.
4. **[!UICONTROL Marketplace Recommendations]**: Verwenden Sie diese Option ähnlich  [!UICONTROL traits] wie die angezeigte, aus  [!UICONTROL Audience Marketplace] Datengebühren, die Sie nicht abonniert haben. Siehe [Audience Marketplace für Datenkäufer](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md), um zu erfahren, wie Sie in [!UICONTROL Marketplace] navigieren und ähnliche Eigenschaften finden.

![basic-property-information](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informationen {#basics}

Der Abschnitt [!UICONTROL Trait Information] enthält Details zu erforderlichen und optionalen Feldern, die Sie beim Erstellen von [!UICONTROL trait] ausgefüllt haben. Dazu gehören Elemente wie [!UICONTROL trait] type, [!UICONTROL trait] ID, description, [!UICONTROL data source] und andere Metadaten. Diese Details variieren je nach Typ [!UICONTROL trait] ([!UICONTROL folder], [!UICONTROL onboarded] oder [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

Das [!UICONTROL Trait Graph] stellt auf einen Blick Leistungsmetriken für das ausgewählte [!UICONTROL trait] bereit. Halten Sie den Cursor über eine Trendlinie, um weitere Daten für das ausgewählte [!UICONTROL trait] anzuzeigen.

[!UICONTROL Unique Trait Realizations] stellen eine Anzahl individueller Benutzer dar, die dies  [!UICONTROL trait] ihrem Profil über einen bestimmten Zeitraum hinzugefügt haben. Das [!UICONTROL Total Trait Population] gibt die Anzahl der Unique Users an, die derzeit für dieses [!UICONTROL trait] qualifiziert sind.

Bei [!UICONTROL rule-based traits] erfolgt die [!UICONTROL trait]-Qualifizierung in Echtzeit, da Benutzer sich für eine [!UICONTROL trait]-Qualifikation in ihrem Browser qualifizieren.

Bei [!UICONTROL onboarded traits] erfolgt die [!UICONTROL trait]-Qualifizierung nach der Verarbeitung einer eingehenden Datei, d. h. die eingehende Datei wird [in Audience Manager](../../faq/faq-inbound-data-ingestion.md) eingezogen, und zwar dann, wenn die [!UICONTROL trait]-Qualifikation erfolgt.

Das [!UICONTROL Trait Graph] zeigt die folgenden Informationen an:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: Wählen Sie diese Option, um die Ergebnisse  [!UICONTROL traits] zu sehen, die Daten für authentifizierte Profil erfassen. Wenn Sie diese Option auswählen, werden nur Daten im Bericht [!UICONTROL Cross-Device ID] angezeigt, und unter dem Bericht [!UICONTROL Device ID] werden keine Daten angezeigt.
   * **[!UICONTROL Device ID]**: Wählen Sie diese Option, um die Ergebnisse  [!UICONTROL traits] zu sehen, die Daten für Geräte-Profil erfassen. Wenn Sie diese Option auswählen, werden nur Daten im Bericht [!UICONTROL Device ID] angezeigt, und unter dem Bericht [!UICONTROL Cross-Device ID] werden keine Daten angezeigt.

      ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Anzahl der Unique Users, die dies über einen bestimmten Zeitraum  [!UICONTROL trait] zu ihrem Profil hinzugefügt haben.
* **[!UICONTROL Total Trait Population]**: Die Anzahl der Unique Users, die derzeit für diese Einstellung qualifiziert sind  [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: Die ersten drei Einträge zeigen die drei Top  [!UICONTROL cross-device data sources] mit der höchsten Bevölkerungszahl, die sich für die  [!UICONTROL trait]in absteigender Reihenfolge qualifiziert haben. Der vierte Eintrag zeigt die Summe aller anderen [!DNL DPUUIDs] ([!DNL CRM IDs]), die für [!UICONTROL trait] qualifiziert sind, von den [!UICONTROL cross-device data sources], die nicht in den oberen drei. Dieser Bericht wird nur angezeigt, wenn Sie im Dropdown-Menü [!UICONTROL Show Results By] oben rechts auf der Seite [!UICONTROL Cross-device ID] &lt;a0/> auswählen. Die Standard-Dropdown-Option ist [!UICONTROL Device ID], bei der dieser Bericht nicht angezeigt wird.

   ![trait-graph](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager zeigt nur dann den Bericht [!UICONTROL Identity Type Breakdown] an, wenn [!UICONTROL cross-device]-IDs für [!UICONTROL trait] qualifiziert sind.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Ausdruck {#trait-expression}

Der Abschnitt [!UICONTROL Trait Expression] zeigt Ihnen die Kriterien an, die Benutzer erfüllen müssen, um sich für [!UICONTROL trait] zu qualifizieren. Diese Regeln werden festgelegt, wenn Sie [eine Eigenschaft](../../features/traits/about-trait-builder.md) erstellen oder bearbeiten.

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segmente {#trait-segments}

Der Abschnitt [!UICONTROL Segments with this Trait] Liste alle Segmente, zu denen das ausgewählte [!UICONTROL trait] gehört. Sie können auf einen Segmentnamen klicken, um Details zu diesem Segment anzuzeigen.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Audit-/Verlaufsprotokoll  {#trait-audit-history}

Für [!UICONTROL rule-based] und [!UICONTROL onboarded traits] zeigt [!UICONTROL Trait Expression Change History] die letzten 10 Änderungen an [!UICONTROL trait]-Ausdruck-Regeln und wer sie vorgenommen hat. Wenn Sie mehr als 10 Änderungen an Ihrem [!UICONTROL trait] vorgenommen haben, klicken Sie auf **[!UICONTROL Export to CSV]**, um das gesamte Prüfprotokoll herunterzuladen. Das Prüfprotokoll steht nicht für [!UICONTROL folder] oder [!UICONTROL algorithmic traits] zur Verfügung.

>[!NOTE]
>
>[!UICONTROL Not Available] in der  [!UICONTROL By User] Spalte bedeutet, dass das Konto für diesen Benutzer gelöscht wurde.

![](assets/traitHistory.png)
---
description: Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie den Eigenschaftsnamen, die ID, Leistungsmetriken, Ausdrücke, die die Eigenschaft definieren, die Segmente, zu denen sie gehört, und das Audit-Protokoll für Eigenschaften. Um diese Details anzuzeigen, gehen Sie zu Zielgruppendaten > Eigenschaften und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: Eigenschaftendetailseite
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: Aufschlüsselung des Identitätstyps, Identitätsaufschlüsselung, Berichte zur Zielgruppen-Identität, geräteübergreifend, geräteübergreifende ID, Geräte-ID
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 0%

---

# [!UICONTROL Trait] {#trait-details-page}

Die Detailseite für eine einzelne [!UICONTROL trait] bietet einen Überblick über die [!UICONTROL trait], z. B. den [!UICONTROL trait], die ID, Leistungsmetriken, Ausdrücke, die die [!UICONTROL trait] definieren, Segmente, zu denen sie gehört, und das [!UICONTROL trait]. Um diese Details anzuzeigen, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** und klicken Sie auf den Namen der [!UICONTROL trait], mit der Sie arbeiten möchten.

## Tools zur [!UICONTROL Trait] {#trait-management-tools}

Oben auf der Seite mit den [!UICONTROL trait] Details befinden sich die Tools, mit denen Sie Ihre [!UICONTROL traits] verwalten können:

1. **[!UICONTROL Add New]**: Verwenden Sie diese Option, um neue [!UICONTROL rule-based], [!UICONTROL algorithmic] oder [!UICONTROL onboarded traits] zu erstellen.
2. **[!UICONTROL Edit]**: Verwenden Sie diese Option, um die Konfiguration des aktuellen [!UICONTROL trait] zu ändern.
3. **[!UICONTROL Delete]**: Verwenden Sie diese Option, um den aktuellen [!UICONTROL trait] aus Ihrem Audience Manager-Konto zu entfernen.
4. **[!UICONTROL Marketplace Recommendations]**: Verwenden Sie diese Option, um ähnliche [!UICONTROL traits] zu finden wie die, die Sie anzeigen, aus [!UICONTROL Audience Marketplace] Datengebühren, die Sie nicht abonniert haben. Unter [Audience Marketplace für Datenkäufer](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) erfahren Sie, wie Sie in der [!UICONTROL Marketplace] navigieren und ähnliche Eigenschaften finden.

![basic-trait-information](assets/basic-trait-information.png)

## [!UICONTROL Trait] {#basics}

Der Abschnitt [!UICONTROL Trait Information] enthält Details zu erforderlichen und optionalen Feldern, die Sie beim Erstellen der [!UICONTROL trait] ausgefüllt haben. Dazu gehören Dinge wie der [!UICONTROL trait], die [!UICONTROL trait]-ID, die Beschreibung, die [!UICONTROL data source] und andere Metadaten. Diese Details variieren je nach [!UICONTROL trait] ([!UICONTROL folder], [!UICONTROL onboarded] oder [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

Die [!UICONTROL Trait Graph] bietet Leistungsmetriken auf einen Blick für Ihre ausgewählten [!UICONTROL trait]. Halten Sie den Cursor über eine Trendlinie, um zusätzliche Daten für die ausgewählte [!UICONTROL trait] anzuzeigen.

[!UICONTROL Unique Trait Realizations] stellen die Anzahl der eindeutigen Benutzer dar, die diese [!UICONTROL trait] im angegebenen Zeitraum zu ihrem Profil hinzugefügt haben. Das [!UICONTROL Total Trait Population] gibt die Anzahl der eindeutigen Benutzer an, die sich derzeit für dieses [!UICONTROL trait] qualifiziert haben.

[!UICONTROL rule-based traits] erfolgt [!UICONTROL trait] Qualifizierung in Echtzeit, da Benutzende für eine [!UICONTROL trait] in ihrem Browser qualifiziert sind.

[!UICONTROL onboarded traits] erfolgt [!UICONTROL trait] Qualifizierung, nachdem eine eingehende Datei verarbeitet wurde, d. h. die eingehende Datei wird [in den Audience Manager eingespeist](../../faq/faq-inbound-data-ingestion.md) und zwar dann, wenn die [!UICONTROL trait] Qualifizierung erfolgt.

Die [!UICONTROL Trait Graph] zeigt die folgenden Informationen an:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: Wählen Sie diese Option aus, um Ergebnisse für [!UICONTROL traits] anzuzeigen, die Daten für authentifizierte Profile erfassen. Wenn Sie diese Option auswählen, werden nur Daten im [!UICONTROL Cross-Device ID] Bericht angezeigt, und es sind keine Daten unter dem [!UICONTROL Device ID] Bericht vorhanden.
   * **[!UICONTROL Device ID]**: Wählen Sie diese Option aus, um Ergebnisse für [!UICONTROL traits] anzuzeigen, die Daten für Geräteprofile erfassen. Wenn Sie diese Option auswählen, werden nur Daten im [!UICONTROL Device ID] Bericht angezeigt, und es sind keine Daten unter dem [!UICONTROL Cross-Device ID] Bericht vorhanden.

     ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Anzahl der eindeutigen Benutzer, die diese [!UICONTROL trait] im angegebenen Zeitraum zu ihrem Profil hinzugefügt haben.
* **[!UICONTROL Total Trait Population]**: Die Anzahl der eindeutigen Benutzer, die sich derzeit für dieses [!UICONTROL trait] qualifiziert haben.

* **[!UICONTROL Identity Type Breakdown]**: Die ersten drei Einträge zeigen die drei wichtigsten [!UICONTROL cross-device data sources] mit der höchsten Populationsanzahl, die sich für die [!UICONTROL trait] qualifiziert haben, in absteigender Reihenfolge. Der vierte Eintrag zeigt die Summe aller anderen [!DNL DPUUIDs] ([!DNL CRM IDs]), die sich für die [!UICONTROL trait] qualifiziert haben, aus den [!UICONTROL cross-device data sources], die nicht zu den drei obersten gehören. Dieser Bericht wird nur angezeigt, wenn Sie im Dropdown-Menü [!UICONTROL Show Results By] oben rechts auf der Seite [!UICONTROL Cross-device ID] auswählen. Die standardmäßige Dropdown-Option ist [!UICONTROL Device ID], wenn dieser Bericht nicht angezeigt wird.

  ![trait-graph](assets/trait-identity.png)

  >[!NOTE]
  >
  >Audience Manager zeigt den [!UICONTROL Identity Type Breakdown] nur an, wenn [!UICONTROL cross-device] für die [!UICONTROL trait] qualifizierten IDs vorhanden sind.

  >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Ausdruck {#trait-expression}

Im Abschnitt [!UICONTROL Trait Expression] werden die Kriterien angezeigt, die Benutzer erfüllen müssen, um sich für die [!UICONTROL trait] zu qualifizieren. Diese Regeln werden festgelegt, wenn Sie [eine Eigenschaft erstellen oder bearbeiten](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait] Segmente {#trait-segments}

Im Abschnitt [!UICONTROL Segments with this Trait] werden alle Segmente aufgelistet, zu denen die ausgewählte [!UICONTROL trait] gehört. Sie können auf einen Segmentnamen klicken, um Details zu diesem Segment anzuzeigen.

![](assets/traitSegments.png)

## Audit-/Verlaufsprotokoll [!UICONTROL Trait] {#trait-audit-history}

Für [!UICONTROL rule-based] und [!UICONTROL onboarded traits] zeigt die [!UICONTROL Trait Expression Change History] die letzten 10 Änderungen an [!UICONTROL trait] Ausdrucksregeln und wer sie vorgenommen hat. Wenn Ihr [!UICONTROL trait] mehr als 10 Änderungen aufweist, klicken Sie auf **[!UICONTROL Export to CSV]** , um das gesamte Administratorprotokoll herunterzuladen. Das Auditprotokoll ist für [!UICONTROL folder] oder [!UICONTROL algorithmic traits] nicht verfügbar.

>[!NOTE]
>
>[!UICONTROL Not Available] in der Spalte [!UICONTROL By User] bedeutet, dass das Konto für diesen Benutzer gelöscht wurde.

![](assets/traitHistory.png)

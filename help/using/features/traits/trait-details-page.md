---
description: Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie Eigenschaftsname, ID, Leistungsmetriken, Ausdrücke, die die Eigenschaft definieren, Segmente, zu denen sie gehört, und das Eigenschafts-Auditprotokoll. Um diese Details anzuzeigen, gehen Sie zu Zielgruppendaten > Eigenschaften und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: Eigenschaftendetailseite
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: Aufschlüsselung nach Identitätstyp, Identitätsaufschlüsselung, Berichte zur Zielgruppenidentität, geräteübergreifend, geräteübergreifende ID, Geräte-ID
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 0%

---

# [!UICONTROL Trait] Detailseite {#trait-details-page}

Die Detailseite für ein einzelnes [!UICONTROL trait] bietet einen Überblick über die [!UICONTROL trait]-Details, wie den [!UICONTROL trait]-Namen, die Kennung, Leistungsmetriken, Ausdrücke, die das [!UICONTROL trait] definieren, Segmente, zu denen es gehört, und das [!UICONTROL trait]-Auditprotokoll. Um diese Details anzuzeigen, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** und klicken Sie auf den Namen der [!UICONTROL trait], mit der Sie arbeiten möchten.

## [!UICONTROL Trait] Verwaltungstools {#trait-management-tools}

Am oberen Rand der Detailseite &quot;[!UICONTROL trait]&quot;befinden sich die Tools, die Sie zur Verwaltung Ihrer [!UICONTROL traits] verwenden können:

1. **[!UICONTROL Add New]**: Verwenden Sie diese Option, um neue [!UICONTROL rule-based], [!UICONTROL algorithmic] oder [!UICONTROL onboarded traits] zu erstellen.
2. **[!UICONTROL Edit]**: Mit dieser Option können Sie die Konfiguration der aktuellen [!UICONTROL trait] ändern.
3. **[!UICONTROL Delete]**: Verwenden Sie diese Option, um die aktuelle [!UICONTROL trait] aus Ihrem Audience Manager-Konto zu entfernen.
4. **[!UICONTROL Marketplace Recommendations]**: Verwenden Sie diese Option, um [!UICONTROL traits] der angezeigten zu ähneln, und zwar aus [!UICONTROL Audience Marketplace] Datengebühren, die Sie nicht abonniert haben. Unter [Audience Marketplace für Datenkäufer](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) erfahren Sie, wie Sie in der [!UICONTROL Marketplace] navigieren und ähnliche Eigenschaften finden.

![basic-trait-information](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informationen {#basics}

Der Abschnitt [!UICONTROL Trait Information] enthält Details zu erforderlichen und optionalen Feldern, die Sie beim Erstellen des [!UICONTROL trait] ausgefüllt haben. Dazu gehören Elemente wie der Typ [!UICONTROL trait], [!UICONTROL trait] ID, Beschreibung, [!UICONTROL data source] und andere Metadaten. Diese Details variieren je nach [!UICONTROL trait] Typ ([!UICONTROL folder], [!UICONTROL onboarded] oder [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

Der [!UICONTROL Trait Graph] bietet einen Überblick über die Leistungsmetriken für Ihren ausgewählten [!UICONTROL trait]. Halten Sie den Cursor über eine Trendlinie, um zusätzliche Daten für die ausgewählte [!UICONTROL trait] anzuzeigen.

[!UICONTROL Unique Trait Realizations] stellt eine Anzahl von Unique Users dar, die ihrem Profil diesen [!UICONTROL trait] im angegebenen Zeitraum hinzugefügt haben. Der [!UICONTROL Total Trait Population] gibt die Anzahl der Unique Users an, die derzeit für diesen [!UICONTROL trait] qualifiziert sind.

Für [!UICONTROL rule-based traits] wird die [!UICONTROL trait] Qualifizierung in Echtzeit durchgeführt, da Benutzer sich für eine [!UICONTROL trait] in ihrem Browser qualifizieren.

Für [!UICONTROL onboarded traits] wird die [!UICONTROL trait] -Qualifizierung ausgeführt, nachdem eine eingehende Datei verarbeitet wurde, d. h., die eingehende Datei wird [ in Audience Manager](../../faq/faq-inbound-data-ingestion.md) eingespeist und die [!UICONTROL trait]-Qualifizierung erfolgt.

Der [!UICONTROL Trait Graph] zeigt die folgenden Informationen an:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: Wählen Sie diese Option aus, um Ergebnisse für [!UICONTROL traits] anzuzeigen, die Daten für authentifizierte Profile erfassen. Wenn Sie diese Option auswählen, werden nur Daten aus dem [!UICONTROL Cross-Device ID] -Bericht angezeigt und keine Daten aus dem [!UICONTROL Device ID] -Bericht.
   * **[!UICONTROL Device ID]**: Wählen Sie diese Option aus, um Ergebnisse für [!UICONTROL traits] anzuzeigen, die Daten für Geräteprofile erfassen. Wenn Sie diese Option auswählen, werden nur Daten aus dem [!UICONTROL Device ID] -Bericht angezeigt und keine Daten aus dem [!UICONTROL Cross-Device ID] -Bericht.

     ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Eine Anzahl von Unique Users, die ihrem Profil diesen [!UICONTROL trait] im angegebenen Zeitraum hinzugefügt haben.
* **[!UICONTROL Total Trait Population]**: Die Anzahl der Unique Users, die derzeit für diesen [!UICONTROL trait] qualifiziert sind.

* **[!UICONTROL Identity Type Breakdown]**: Die ersten drei Einträge zeigen die drei oberen [!UICONTROL cross-device data sources] mit der höchsten Anzahl an Populationen, die sich für die [!UICONTROL trait] qualifiziert haben, in absteigender Reihenfolge. Der vierte Eintrag zeigt die Summe aller anderen [!DNL DPUUIDs] ([!DNL CRM IDs]), die sich für die [!UICONTROL trait] qualifiziert haben, von den [!UICONTROL cross-device data sources], die nicht zu den oberen drei gehören. Dieser Bericht wird nur angezeigt, wenn Sie im Dropdownmenü [!UICONTROL Show Results By] oben rechts auf der Seite die Option [!UICONTROL Cross-device ID] auswählen. Die standardmäßige Dropdown-Option ist [!UICONTROL Device ID], wobei dieser Bericht nicht angezeigt wird.

  ![trait-graph](assets/trait-identity.png)

  >[!NOTE]
  >
  >Audience Manager zeigt nur den Bericht [!UICONTROL Identity Type Breakdown] an, wenn Sie [!UICONTROL cross-device] IDs für die [!UICONTROL trait] qualifiziert haben.

  >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Ausdruck {#trait-expression}

Im Abschnitt [!UICONTROL Trait Expression] werden die Kriterien angezeigt, die Benutzer erfüllen müssen, um sich für die [!UICONTROL trait] zu qualifizieren. Diese Regeln werden festgelegt, wenn Sie [eine Eigenschaft erstellen oder bearbeiten](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait] Segmente {#trait-segments}

Im Abschnitt [!UICONTROL Segments with this Trait] werden alle Segmente aufgelistet, zu denen die ausgewählte [!UICONTROL trait] gehört. Sie können auf einen Segmentnamen klicken, um Details zu diesem Segment anzuzeigen.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Audit-/Verlaufsprotokoll {#trait-audit-history}

Für [!UICONTROL rule-based] und [!UICONTROL onboarded traits] zeigt die [!UICONTROL Trait Expression Change History] die letzten 10 Änderungen an den [!UICONTROL trait]-Ausdrucksregeln an und wer sie vorgenommen hat. Wenn Ihr [!UICONTROL trait] mehr als 10 Änderungen enthält, klicken Sie auf **[!UICONTROL Export to CSV]** , um das gesamte Auditprotokoll herunterzuladen. Das Prüfprotokoll ist nicht für [!UICONTROL folder] oder [!UICONTROL algorithmic traits] verfügbar.

>[!NOTE]
>
>[!UICONTROL Not Available] in der Spalte [!UICONTROL By User] bedeutet, dass das Konto für diesen Benutzer gelöscht wurde.

![](assets/traitHistory.png)

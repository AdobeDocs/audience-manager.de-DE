---
description: Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie Eigenschaftsname, ID, Leistungsmetriken, Ausdrücke, die die Eigenschaft definieren, Segmente, zu denen sie gehört, und das Eigenschafts-Auditprotokoll. Um diese Details anzuzeigen, gehen Sie zu Zielgruppendaten > Eigenschaften und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.
seo-description: Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie Eigenschaftsname, ID, Leistungsmetriken, Ausdrücke, die die Eigenschaft definieren, Segmente, zu denen sie gehört, und das Eigenschafts-Auditprotokoll. Um diese Details anzuzeigen, gehen Sie zu Zielgruppendaten > Eigenschaften und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.
seo-title: Detailseite einer Eigenschaft
solution: Audience Manager
title: Detailseite einer Eigenschaft
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: Aufschlüsselung nach Identitätstyp, Identitätsaufschlüsselung, Berichte zur Zielgruppenidentität, geräteübergreifend, geräteübergreifende ID, Geräte-ID
feature: 'Eigenschaften '
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 1%

---

# [!UICONTROL Trait] Detailseite {#trait-details-page}

Die Detailseite für einen einzelnen [!UICONTROL trait] bietet einen Überblick über die [!UICONTROL trait]-Details, wie z. B. den [!UICONTROL trait]-Namen, die -ID, die Leistungsmetriken, die Ausdrücke, die die [!UICONTROL trait] definieren, die zugehörigen Segmente und das [!UICONTROL trait]-Auditprotokoll. Um diese Details anzuzeigen, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** und klicken Sie auf den Namen des [!UICONTROL trait], mit dem Sie arbeiten möchten.

## [!UICONTROL Trait] Management-Tools {#trait-management-tools}

Am Anfang der Detailseite [!UICONTROL trait] befinden sich die Tools, die Sie zum Verwalten Ihrer [!UICONTROL traits] verwenden können:

1. **[!UICONTROL Add New]**: Verwenden Sie diese Option, um neue  [!UICONTROL rule-based],  [!UICONTROL algorithmic] oder  [!UICONTROL onboarded traits]zu erstellen.
2. **[!UICONTROL Edit]**: Verwenden Sie diese Option, um die Konfiguration der aktuellen  [!UICONTROL trait]zu ändern.
3. **[!UICONTROL Delete]**: Verwenden Sie diese Option, um die aktuelle Version  [!UICONTROL trait] aus Ihrem Audience Manager-Konto zu entfernen.
4. **[!UICONTROL Marketplace Recommendations]**: Verwenden Sie diese Option ähnlich  [!UICONTROL traits] der angezeigten, aus  [!UICONTROL Audience Marketplace] Datengebühren, die Sie nicht abonniert haben. Siehe [Audience Marketplace für Datenkäufer](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) , um zu erfahren, wie Sie in [!UICONTROL Marketplace] navigieren und ähnliche Eigenschaften finden.

![basic-trait-information](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informationen {#basics}

Der Abschnitt [!UICONTROL Trait Information] enthält Details zu erforderlichen und optionalen Feldern, die Sie beim Erstellen von [!UICONTROL trait] ausgefüllt haben. Dazu gehören Elemente wie der Typ [!UICONTROL trait], [!UICONTROL trait] ID, Beschreibung, [!UICONTROL data source] und andere Metadaten. Diese Details variieren je nach Typ [!UICONTROL trait] ([!UICONTROL folder], [!UICONTROL onboarded] oder [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph] bietet einen Überblick über Leistungsmetriken für Ihre ausgewählte [!UICONTROL trait]. Halten Sie den Cursor über eine Trendlinie, um zusätzliche Daten für das ausgewählte [!UICONTROL trait] anzuzeigen.

[!UICONTROL Unique Trait Realizations] stellen eine Anzahl von Unique Users dar, die dieses  [!UICONTROL trait] zu ihrem Profil über den angegebenen Zeitraum hinzugefügt haben. [!UICONTROL Total Trait Population] gibt die Anzahl der Unique Users an, die sich derzeit für dieses [!UICONTROL trait] qualifiziert haben.

Für [!UICONTROL rule-based traits] erfolgt die [!UICONTROL trait]-Qualifizierung in Echtzeit, da Benutzer sich für [!UICONTROL trait] in ihrem Browser qualifizieren.

Für [!UICONTROL onboarded traits] erfolgt die [!UICONTROL trait]-Qualifizierung nach der Verarbeitung einer eingehenden Datei, d. h. die eingehende Datei wird [in den Audience Manager ](../../faq/faq-inbound-data-ingestion.md) eingespeist und die [!UICONTROL trait]-Qualifizierung erfolgt.

[!UICONTROL Trait Graph] zeigt die folgenden Informationen an:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: Wählen Sie diese Option aus, um Ergebnisse für anzuzeigen,  [!UICONTROL traits] die Daten für authentifizierte Profile erfassen. Wenn Sie diese Option auswählen, werden nur Daten aus dem Bericht [!UICONTROL Cross-Device ID] angezeigt und unter dem Bericht [!UICONTROL Device ID] werden keine Daten angezeigt.
   * **[!UICONTROL Device ID]**: Wählen Sie diese Option aus, um Ergebnisse für anzuzeigen,  [!UICONTROL traits] die Daten für Geräteprofile erfassen. Wenn Sie diese Option auswählen, werden nur Daten aus dem Bericht [!UICONTROL Device ID] angezeigt und unter dem Bericht [!UICONTROL Cross-Device ID] werden keine Daten angezeigt.

      ![trait-graph](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Zählung der Unique Users, die das Profil im angegebenen Zeitraum  [!UICONTROL trait] zu diesem hinzugefügt haben.
* **[!UICONTROL Total Trait Population]**: Die Anzahl der Unique Users, die sich derzeit für diese  [!UICONTROL trait]Aktion qualifiziert haben.

* **[!UICONTROL Identity Type Breakdown]**: Die ersten drei Einträge zeigen die drei wichtigsten  [!UICONTROL cross-device data sources] mit der höchsten Populationsanzahl, die sich für die  [!UICONTROL trait]qualifiziert haben, in absteigender Reihenfolge. Der vierte Eintrag zeigt die Summe aller anderen [!DNL DPUUIDs] ([!DNL CRM IDs]), die sich für [!UICONTROL trait] qualifiziert haben, aus den [!UICONTROL cross-device data sources], die nicht in den oberen drei sind. Dieser Bericht wird nur angezeigt, wenn Sie im Dropdownmenü [!UICONTROL Show Results By] oben rechts auf der Seite [!UICONTROL Cross-device ID] die Option  auswählen. Die Standard-Dropdown-Option ist [!UICONTROL Device ID], wobei dieser Bericht nicht angezeigt wird.

   ![trait-graph](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager zeigt nur den Bericht [!UICONTROL Identity Type Breakdown] an, wenn Sie [!UICONTROL cross-device]-IDs für [!UICONTROL trait] qualifiziert haben.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Ausdruck {#trait-expression}

Im Abschnitt [!UICONTROL Trait Expression] werden die Kriterien angezeigt, die Benutzer erfüllen müssen, um sich für [!UICONTROL trait] zu qualifizieren. Diese Regeln werden festgelegt, wenn Sie [eine Eigenschaft](../../features/traits/about-trait-builder.md) erstellen oder bearbeiten.

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segmente  {#trait-segments}

Im Abschnitt [!UICONTROL Segments with this Trait] werden alle Segmente aufgelistet, zu denen die ausgewählte [!UICONTROL trait] gehört. Sie können auf einen Segmentnamen klicken, um Details zu diesem Segment anzuzeigen.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Audit-/Verlaufsprotokoll {#trait-audit-history}

Für [!UICONTROL rule-based] und [!UICONTROL onboarded traits] zeigt [!UICONTROL Trait Expression Change History] die letzten 10 Änderungen an den [!UICONTROL trait]-Ausdrucksregeln an und wer sie vorgenommen hat. Wenn Ihr [!UICONTROL trait] mehr als 10 Änderungen aufweist, klicken Sie auf **[!UICONTROL Export to CSV]** , um das gesamte Auditprotokoll herunterzuladen. Das Auditprotokoll steht nicht für [!UICONTROL folder] oder [!UICONTROL algorithmic traits] zur Verfügung.

>[!NOTE]
>
>[!UICONTROL Not Available] in der  [!UICONTROL By User] Spalte bedeutet, dass das Konto für diesen Benutzer gelöscht wurde.

![](assets/traitHistory.png)

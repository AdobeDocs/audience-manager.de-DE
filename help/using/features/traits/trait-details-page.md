---
description: Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie Eigenschaftsname, ID, Leistungsmetriken, Ausdrücke, die die Eigenschaft definieren, Segmente, zu denen sie gehört, und das Eigenschafts-Prüfprotokoll. Um diese Details anzuzeigen, gehen Sie zu Zielgruppendaten > Eigenschaften und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.
seo-description: Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie Eigenschaftsname, ID, Leistungsmetriken, Ausdrücke, die die Eigenschaft definieren, Segmente, zu denen sie gehört, und das Eigenschafts-Prüfprotokoll. Um diese Details anzuzeigen, gehen Sie zu Zielgruppendaten > Eigenschaften und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.
seo-title: Eigenschaftendetailseite
solution: Audience Manager
title: Eigenschaftendetailseite
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Eigenschaftendetailseite {#trait-details-page}

Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie Eigenschaftsname, ID, Leistungsmetriken, Ausdrücke, die die Eigenschaft definieren, Segmente, zu denen sie gehört, und das Eigenschafts-Prüfprotokoll. Um diese Details anzuzeigen, gehen Sie zu [!UICONTROL Audience Data > Traits] und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.

## Basisinformationen {#basics}

Der [!UICONTROL Basic Information] Abschnitt enthält Details zu erforderlichen und optionalen Feldern, die Sie beim Erstellen der Eigenschaft ausgefüllt haben. Dazu gehören Eigenschaften wie der Eigenschaftstyp, ID der Eigenschaft, Beschreibung, Datenquelle und andere Metadaten. Diese Details variieren je nach Eigenschaftstyp (Ordner, Bordkarte oder regelbasiert).

![](assets/basicInfo.png)

## Eigenschaftsdiagramm {#trait-graph}

Der Bericht [!UICONTROL Trait Graph] enthält Leistungsmetriken auf einen Blick für Ihre ausgewählte Eigenschaft. Halten Sie den Cursor über eine Trendlinie, um weitere Daten für die ausgewählte Eigenschaft anzuzeigen.

[!UICONTROL Unique Trait Realizations] stellen eine Anzahl individueller Benutzer dar, die dieses Merkmal ihrem Profil im angegebenen Zeitraum hinzugefügt haben. Die [!UICONTROL Total Trait Population] gibt die Anzahl der Unique Users an, die derzeit für diese Eigenschaft qualifiziert sind.

* Bei regelbasierten Eigenschaften erfolgt die Qualifizierung von Eigenschaften in Echtzeit, da Benutzer sich für eine Eigenschaft in ihrem Browser qualifizieren.
* Bei Eigenschaften, die nicht an Bord sind, erfolgt die Qualifizierung der Eigenschaften nach der Verarbeitung einer eingehenden Datei, d. h. die eingehende Datei wird an Audience Manager [weitergeleitet](../../faq/faq-inbound-data-ingestion.md) , und zwar dann, wenn die Eigenschaftsqualifikation erfolgt.
* **[!UICONTROL Unique Trait Realizations]**: Anzahl der Unique Users, die diese Eigenschaft im angegebenen Zeitraum ihrem Profil hinzugefügt haben.
* **[!UICONTROL Total Trait Population]**: Die Anzahl der Unique Users, die derzeit für diese Eigenschaft qualifiziert sind.

   ![trait-graph](assets/trait-summary.png)

* **[!UICONTROL Identity Type Breakdown]**: Die ersten drei Einträge zeigen die drei wichtigsten geräteübergreifenden Datenquellen mit der höchsten Bevölkerungszahl, die sich für die Eigenschaft qualifiziert haben, in absteigender Reihenfolge. Der vierte Eintrag zeigt die Summe aller anderen [!DNL DPUUIDs] ([!DNL CRM IDs]), die sich für die Eigenschaft qualifiziert haben, aus den geräteübergreifenden Datenquellen, die nicht zu den drei oberen gehören. Dieser Bericht wird nur angezeigt, wenn Sie im [!UICONTROL Show Results By] Dropdown-Menü oben rechts auf der Seite die Option Geräteübergreifende ID auswählen. Die standardmäßige Dropdown-Option ist [!UICONTROL Device ID]die, bei der dieser Bericht nicht angezeigt wird.

   ![trait-graph](assets/trait-identity.png)
   > [!NOTE]
   > Audience Manager zeigt den [!UICONTROL Identity Type Breakdown] Bericht nur dann an, wenn Sie geräteübergreifende IDs für die Eigenschaft qualifiziert haben.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=ger)

## Eigenschaftsausdruck {#trait-expression}

Der [!UICONTROL Trait Expression] Abschnitt zeigt Ihnen, welche Kriterien Benutzer erfüllen müssen, um sich für die Eigenschaft zu qualifizieren. Diese Regeln werden beim [Erstellen oder Bearbeiten einer Eigenschaft](../../features/traits/about-trait-builder.md)festgelegt.

![](assets/traitExpression.png)

## Eigenschaftensegmente {#trait-segments}

Im [!UICONTROL Segments with this Trait] Abschnitt werden alle Segmente aufgelistet, zu denen die ausgewählten Eigenschaften gehören. Sie können auf einen Segmentnamen klicken, um Details zu diesem Segment anzuzeigen.

![](assets/traitSegments.png)

## Eigenschafts-/Verlaufsprotokoll {#trait-audit-history}

Bei regelbasierten und nicht an Bord befindlichen Eigenschaften [!UICONTROL Trait Expression Change History] zeigt die Tabelle die letzten 10 Änderungen an den Regeln für Eigenschaftsausdrücke an und wer sie vorgenommen hat. Wenn Ihre Eigenschaft mehr als 10 Änderungen aufweist, klicken Sie auf **[!UICONTROL Export to CSV]** , um das gesamte Prüfprotokoll herunterzuladen. Das Prüfprotokoll steht nicht für Ordner- oder algorithmische Eigenschaften zur Verfügung.

>[!NOTE]
>
>[!UICONTROL Not Available] in der [!UICONTROL By User] Spalte bedeutet, dass das Konto für diesen Benutzer gelöscht wurde.

![](assets/traitHistory.png)
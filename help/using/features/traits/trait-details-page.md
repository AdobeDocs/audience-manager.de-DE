---
description: Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie den Eigenschaftsnamen, die ID, die Leistungsmetriken, Ausdrücke, die die Eigenschaft definieren, Segmente, zu denen sie gehören, und das Auditprotokoll des Eigenschaftenprotokolls. Um diese Details zu speichern, gehen Sie zu Zielgruppendaten > Eigenschaften und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.
seo-description: Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie den Eigenschaftsnamen, die ID, die Leistungsmetriken, Ausdrücke, die die Eigenschaft definieren, Segmente, zu denen sie gehören, und das Auditprotokoll des Eigenschaftenprotokolls. Um diese Details zu speichern, gehen Sie zu Zielgruppendaten > Eigenschaften und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.
seo-title: Eigenschaftendetails-Seite
solution: Audience Manager
title: Eigenschaftendetails-Seite
uuid: 23301376-c 1 cc -4778-b 8 c 4-9831 f 6739 db 9
translation-type: tm+mt
source-git-commit: 76adee013246c68da7ad871cef57f6ef174a239c

---


# Eigenschaftendetails-Seite {#trait-details-page}

Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie den Eigenschaftsnamen, die ID, die Leistungsmetriken, Ausdrücke, die die Eigenschaft definieren, Segmente, zu denen sie gehören, und das Auditprotokoll des Eigenschaftenprotokolls. Um diese Details zu speichern, klicken [!UICONTROL Audience Data > Traits] Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.

## Basisinformationen {#basics}

Der [!UICONTROL Basic Information] Abschnitt enthält Details zu erforderlichen und optionalen Feldern, die Sie beim Erstellen der Eigenschaft ausgefüllt haben. Dazu gehören beispielsweise Eigenschaften, Eigenschaften-ID, Beschreibung, Datenquelle und andere Metadaten. Diese Details variieren je nach Eigenschaftstyp (Ordner, Onboarded oder regelbasiert).

![](assets/basicInfo.png)

## Eigenschaftendiagramm {#trait-graph}

Die Funktion [!UICONTROL Trait Graph] bietet eine vordefinierte Leistungsmetrik für die ausgewählte Eigenschaft. Halten Sie den Mauszeiger über eine Trendlinie, um weitere Daten für die ausgewählte Eigenschaft anzuzeigen.

[!UICONTROL Unique Trait Realizations] eine Anzahl Unique Users darstellen, die diese Eigenschaft ihrem Profil über den angegebenen Zeitraum hinzugefügt hat. Die Angabe [!UICONTROL Total Trait Population] gibt die Anzahl der eindeutigen Benutzer an, die derzeit für diese Eigenschaft qualifiziert sind.

* Bei regelbasierten Eigenschaften erfolgt die Eigenschaftsqualifizierung in Echtzeit, da sich Benutzer für eine Eigenschaft in ihrem Browser qualifizieren.
* Bei Onboardanmerkungen erfolgt die Trait-Qualifizierung nach der Verarbeitung einer Inbound-Datei, d. h., die Inbound-Datei [wird in Audience Manager gespeist,](../../faq/faq-inbound-data-ingestion.md) d. h., die Eigenschaftsqualifikation wird ausgeführt.
* **[!UICONTROL Unique Trait Realizations]**: Eine Anzahl Unique Users, die diese Eigenschaft im angegebenen Zeitraum ihrem Profil hinzugefügt hat.
* **[!UICONTROL Total Trait Population]**: Die Anzahl der Unique Users, die derzeit für diese Eigenschaft qualifiziert sind.

   ![trait-graph](assets/trait-summary.png)

* **[!UICONTROL Identity Type Breakdown]**: Die ersten drei Einträge zeigen die drei geräteübergreifenden Datenquellen mit der höchsten Anzahl an Einwohnern, die für die Eigenschaft qualifiziert sind, in absteigender Reihenfolge. Der vierte Eintrag zeigt die Summe aller anderen [!DNL DPUUIDs] ([!DNL CRM IDs]), die für die Eigenschaft qualifiziert sind, aus den geräteübergreifenden Datenquellen, die nicht in den Top -3-Apps enthalten sind. Dieser Bericht wird nur angezeigt, wenn Sie im [!UICONTROL Show Results By] Dropdown-Menü rechts oben auf der Seite die Option "Geräteübergreifende ID" auswählen. Die standarddropdown-Option ist [!UICONTROL Device ID], wo dieser Bericht nicht angezeigt wird.

   ![trait-graph](assets/trait-identity.png)
   > [!NOTE]
   > Audience Manager zeigt den [!UICONTROL Identity Type Breakdown] Bericht nur an, wenn Sie über geräteübergreifende IDs verfügen, die für die Eigenschaft qualifiziert sind.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/?captions=ger)

## Eigenschafts-Ausdruck {#trait-expression}

Der [!UICONTROL Trait Expression] Abschnitt zeigt Ihnen die Kriterien, die Benutzer erfüllen müssen, um die Eigenschaft zu qualifizieren. Diese Regeln werden festgelegt, wenn Sie [eine Eigenschaft erstellen oder bearbeiten](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Eigenschaftssegmente {#trait-segments}

Der [!UICONTROL Segments with this Trait] Abschnitt listet alle Segmente auf, zu denen die ausgewählte Eigenschaft gehört. Sie können auf einen Segmentnamen klicken, um Details zu diesem Segment anzuzeigen.

![](assets/traitSegments.png)

## Eigenschafts-/Protokollprotokoll {#trait-audit-history}

Bei regelbasierten und onboardierten Eigenschaften [!UICONTROL Trait Expression Change History] werden Ihnen die letzten 10 Änderungen angezeigt, die an den Eigenschaftsregeln vorgenommen wurden und wer sie vorgenommen hat. Wenn Ihr Merkmal mehr als 10 Änderungen aufweist, klicken Sie auf, **[!UICONTROL Export to CSV]** um das gesamte Prüfprotokoll herunterzuladen. Das Auditprotokoll ist nicht für Ordner oder algorithmische Eigenschaften verfügbar.

>[!NOTE]
>
>[!UICONTROL Not Available] in der [!UICONTROL By User] Spalte bedeutet, dass das Konto für diesen Benutzer gelöscht wurde.

![](assets/traitHistory.png)
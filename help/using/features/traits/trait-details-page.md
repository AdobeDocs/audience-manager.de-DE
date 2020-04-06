---
description: Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie Eigenschaftsname, ID, Leistungsmetriken, Ausdruck, die die Eigenschaft definieren, Segmente, zu denen sie gehört, und das Eigenschafts-Prüfprotokoll. Um diese Details anzuzeigen, gehen Sie zu "Audience-Daten"> "Eigenschaften"und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.
seo-description: Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über Informationen wie Eigenschaftsname, ID, Leistungsmetriken, Ausdruck, die die Eigenschaft definieren, Segmente, zu denen sie gehört, und das Eigenschafts-Prüfprotokoll. Um diese Details anzuzeigen, gehen Sie zu "Audience-Daten"> "Eigenschaften"und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.
seo-title: Eigenschaftendetailseite
solution: Audience Manager
title: Eigenschaftendetailseite
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# Eigenschaftendetailseite {#trait-details-page}

Die Detailseite für eine einzelne Eigenschaft bietet einen Überblick über die Eigenschaftendetails, wie den Eigenschaftsnamen, die ID, die Leistungsmetriken, die Ausdruck, die die Eigenschaft definieren, die Segmente, zu denen sie gehört, und das Eigenschafts-Prüfprotokoll. Um diese Details Ansicht, gehen Sie zu **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** und klicken Sie auf den Namen der Eigenschaft, mit der Sie arbeiten möchten.

## Eigenschaftsverwaltungswerkzeuge {#trait-management-tools}

Oben auf der Seite mit den Eigenschaftendetails befinden sich die Werkzeuge, mit denen Sie Ihre Eigenschaften verwalten können:

1. **[!UICONTROL Add New]**: Verwenden Sie diese Option, um neue regelbasierte, algorithmische oder Onboard-Eigenschaften zu erstellen.
2. **[!UICONTROL Edit]**: Verwenden Sie diese Option, um die Konfiguration der aktuellen Eigenschaft zu ändern.
3. **[!UICONTROL Delete]**: Verwenden Sie diese Option, um die aktuelle Eigenschaft aus Ihrem Audience Manager-Konto zu entfernen.
4. **[!UICONTROL Marketplace Recommendations]**: Verwenden Sie diese Option, um ähnliche Eigenschaften wie die, die Sie anzeigen, aus [!UICONTROL Audience Marketplace] Datengebühren zu finden, die Sie nicht abonniert haben. Unter [Audience Marketplace for Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) erfahren Sie, wie Sie auf dem Markt navigieren und ähnliche Eigenschaften finden.

![basic-property-information](assets/basic-trait-information.png)

## Eigenschaften-Informationen {#basics}

Der [!UICONTROL Trait Information] Abschnitt enthält Details zu erforderlichen und optionalen Feldern, die Sie beim Erstellen der Eigenschaft ausgefüllt haben. Dazu gehören Eigenschaften wie der Eigenschaftstyp, ID der Eigenschaft, Beschreibung, Datenquelle und andere Metadaten. Diese Details variieren je nach Eigenschaftstyp (Ordner, Bordkarte oder regelbasiert).

## Eigenschaftsdiagramm {#trait-graph}

Der Bericht [!UICONTROL Trait Graph] enthält Leistungsmetriken auf einen Blick für Ihre ausgewählte Eigenschaft. Halten Sie den Cursor über eine Trendlinie, um weitere Daten für die ausgewählte Eigenschaft anzuzeigen.

[!UICONTROL Unique Trait Realizations] stellen eine Anzahl individueller Benutzer dar, die ihr Profil über einen bestimmten Zeitraum mit dieser Eigenschaft versehen haben. Die [!UICONTROL Total Trait Population] gibt die Anzahl der Unique Users an, die derzeit für diese Eigenschaft qualifiziert sind.

* Bei regelbasierten Eigenschaften erfolgt die Qualifizierung von Eigenschaften in Echtzeit, da Benutzer sich für eine Eigenschaft in ihrem Browser qualifizieren.
* Bei Eigenschaften, die nicht an Bord sind, erfolgt die Qualifizierung der Eigenschaften nach der Verarbeitung einer eingehenden Datei, d. h. die eingehende Datei wird in den Audience Manager [](../../faq/faq-inbound-data-ingestion.md) eingespeist, und zwar dann, wenn die Eigenschaftsqualifikation erfolgt.
* **[!UICONTROL Unique Trait Realizations]**: Anzahl der Unique Users, die dieses Merkmal ihrem Profil über einen bestimmten Zeitraum hinzugefügt haben.
* **[!UICONTROL Total Trait Population]**: Die Anzahl der Unique Users, die derzeit für diese Eigenschaft qualifiziert sind.

   ![trait-graph](assets/trait-summary.png)

* **[!UICONTROL Identity Type Breakdown]**: Die ersten drei Einträge zeigen die drei wichtigsten geräteübergreifenden Datenquellen mit der höchsten Bevölkerungszahl, die sich für die Eigenschaft qualifiziert haben, in absteigender Reihenfolge. Der vierte Eintrag zeigt die Summe aller anderen [!DNL DPUUIDs] ([!DNL CRM IDs]), die sich für die Eigenschaft qualifiziert haben, aus den geräteübergreifenden Datenquellen, die nicht zu den drei oberen gehören. Dieser Bericht wird nur angezeigt, wenn Sie im [!UICONTROL Show Results By] Dropdown-Menü oben rechts auf der Seite die Option Geräteübergreifende ID auswählen. Die standardmäßige Dropdown-Option ist [!UICONTROL Device ID]die, bei der dieser Bericht nicht angezeigt wird.

   ![trait-graph](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager zeigt den [!UICONTROL Identity Type Breakdown] Bericht nur dann an, wenn Sie geräteübergreifende IDs für die Eigenschaft qualifiziert haben.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## Eigenschaften-Ausdruck {#trait-expression}

Der [!UICONTROL Trait Expression] Abschnitt zeigt Ihnen, welche Kriterien Benutzer erfüllen müssen, um sich für die Eigenschaft zu qualifizieren. Diese Regeln werden festgelegt, wenn Sie eine Eigenschaft [erstellen oder bearbeiten](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Eigenschaftensegmente {#trait-segments}

Der [!UICONTROL Segments with this Trait] Abschnitt Liste alle Segmente, zu denen die Eigenschaft gehört. Sie können auf einen Segmentnamen klicken, um Details zu diesem Segment anzuzeigen.

![](assets/traitSegments.png)

## Eigenschafts-/Verlaufsprotokoll {#trait-audit-history}

Bei regelbasierten und nicht an Bord befindlichen Eigenschaften [!UICONTROL Trait Expression Change History] zeigt die Seite die letzten 10 Änderungen an den Eigenschaftsregeln und wer sie vorgenommen hat. Wenn Ihre Eigenschaft mehr als 10 Änderungen aufweist, klicken Sie auf **[!UICONTROL Export to CSV]** , um das gesamte Prüfprotokoll herunterzuladen. Das Prüfprotokoll steht nicht für Ordner- oder algorithmische Eigenschaften zur Verfügung.

>[!NOTE]
>
>[!UICONTROL Not Available] in der [!UICONTROL By User] Spalte bedeutet, dass das Konto für diesen Benutzer gelöscht wurde.

![](assets/traitHistory.png)
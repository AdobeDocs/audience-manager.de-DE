---
description: Um eine neue Datenquelle zu erstellen, gehen Sie zu Zielgruppendaten > Datenquellen > Neu hinzufügen und führen Sie die Schritte für jeden hier beschriebenen Abschnitt aus. Zum Erstellen einer Datenquelle sind Administratorrechte erforderlich.
keywords: cdf; benutzerspezifischer Datenfeed
seo-description: Um eine neue Datenquelle zu erstellen, gehen Sie zu Zielgruppendaten > Datenquellen > Neu hinzufügen und führen Sie die Schritte für jeden hier beschriebenen Abschnitt aus. Zum Erstellen einer Datenquelle sind Administratorrechte erforderlich.
seo-title: Datenquelle erstellen
solution: Audience Manager
title: Datenquelle erstellen
uuid: 4 df 65 bcb -9 ad 9-4 b 72-a 71 e -8918 b 43 d 4850
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Datenquellen verwalten {#manage-data-sources}

## Datenquelle erstellen {#create-data-source}

Um eine neue Datenquelle zu erstellen, gehen **[!UICONTROL Audience Data > Data Sources > Add New]** Sie zu den Schritten, die Sie hier beschrieben haben. Zum Erstellen einer Datenquelle sind Administratorrechte erforderlich.

<!-- create-datasource.xml -->

>[!TIP]
>
>Beschreibungen dieser verschiedenen Steuerelemente finden Sie unter [Datenquelleneinstellungen und Menüoptionen](../features/datasources-list-and-settings.md#settings-menu-options) .

## Datenquellendetails {#details}

So füllen Sie den [!UICONTROL Data Source Details] Abschnitt aus:

1. Benennen Sie die Datenquelle.
1. *(Optional)* Beschreiben Sie die Datenquelle. Eine knappe Beschreibung hilft Ihnen, die Rolle oder den Zweck der Datenquelle zu definieren.
1. Geben Sie einen Integrationscode an. Integrationscodes sind im Allgemeinen optional. Sie sind erforderlich, wenn Sie:

   * [Erstellen Sie eine geräteübergreifende Datenquelle](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Verwenden Sie den [Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/).
   * Arbeiten mit [Profilzusammenführungsregeln](../features/profile-merge-rules/merge-rules-start.md).

1. Wählen Sie eine **[!UICONTROL ID Type]**. Zu den Optionen für den ID-Typ gehören:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Erforderlich zum Erstellen von [!UICONTROL Profile Merge Rule]). Hinweis: Bei einigen Kunden stellt diese Auswahl die **[!UICONTROL ID Definition]** Optionen bereit.

1. Wählen Sie eine **[!UICONTROL ID Definition]** Option. Zu den Optionen zählen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Datenexportkontrolle {#export-controls}

[Datenexportsteuerelemente](../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine Datenquelle und ein Ziel anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion einen Datenschutz verletzt oder Vereinbarung verwendet. Überspringen Sie diesen Abschnitt, wenn Sie nicht verwenden [!UICONTROL Data Export Controls].

## Datenquelleneinstellungen {#settings}

Diese Einstellungen bestimmen, wie eine Datenquelle identifiziert, verwendet und freigegeben wird. Sie können auch Fehlerberichte für eingehende Datendateien aktivieren. So füllen Sie den [!UICONTROL Data Source Settings] Abschnitt aus:

1. Aktivieren Sie ein [!UICONTROL Data Source Setting] Kontrollkästchen, um eine Option auf Ihre Datenquelle anzuwenden.
2. Klicken Sie auf **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Datenquelleneinstellungen und Menüoptionen](../features/datasources-list-and-settings.md#settings-menu-options)


## Datenquelle löschen {#delete-data-source}

<!-- t_datasource_delete.xml -->

Löschen Sie eine Datenquelle, die Sie nicht mehr benötigen.

>[!NOTE]
>
>Bitte beachten Sie die folgenden Einschränkungen:
>
>* Sie können [eine aktive Zielgruppe oder Datenquelle-Synchronisierung nicht löschen](../features/traits/client-activity-synced-audience-traits.md).
>* Für Kunden, die Adobe Analytics verwenden: In Audience Manager können Sie nicht automatisch aus Ihren [!DNL Analytics] Report Suites erstellte Datenquellen löschen. Mit dem [Core-Service](https://marketing.adobe.com/resources/help/en_US/mcloud/) können Sie die Zuordnung dieser Datenquellen aufheben.


1. Klicken Sie **[!UICONTROL Audience Data]** auf &gt; **[!UICONTROL Data Sources]**.
1. Aktivieren Sie das Kontrollkästchen neben einer oder mehreren Datenquellen.
Sie können das [!UICONTROL Search] Kästchen verwenden, um die gewünschten Datenquellen zu finden, wenn Sie eine lange Liste haben.
1. Klicken ![](assets/icon_trash.png)Sie auf und bestätigen Sie dann den Löschvorgang.
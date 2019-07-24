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


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

To create a new data source, go to **[!UICONTROL Audience Data > Data Sources > Add New]** and complete the steps for each section described here. Zum Erstellen einer Datenquelle sind Administratorrechte erforderlich.

<!-- create-datasource.xml -->

>[!TIP]
>
>See [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options) for descriptions of these different controls.

## Data Source Details {#details}

To complete the [!UICONTROL Data Source Details] section:

1. Benennen Sie die Datenquelle.
1. *(Optional)* Beschreiben Sie die Datenquelle. Eine knappe Beschreibung hilft Ihnen, die Rolle oder den Zweck der Datenquelle zu definieren.
1. Geben Sie einen Integrationscode an. Integrationscodes sind im Allgemeinen optional. Sie sind erforderlich, wenn Sie:

   * [Erstellen Sie eine geräteübergreifende Datenquelle](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Use the [Experience Cloud ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
   * Work with [Profile Merge Rules](../features/profile-merge-rules/merge-rules-start.md).

1. Choose an **[!UICONTROL ID Type]**. Zu den Optionen für den ID-Typ gehören:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Erforderlich zum Erstellen von [!UICONTROL Profile Merge Rule]). Note, for some customers, this selection exposes the **[!UICONTROL ID Definition]** options.

1. Choose an **[!UICONTROL ID Definition]** option. Zu den Optionen zählen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Datenexportkontrolle {#export-controls}

[Datenexportsteuerelemente](../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine Datenquelle und ein Ziel anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion einen Datenschutz verletzt oder Vereinbarung verwendet. Skip this section if you do not use [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

Diese Einstellungen bestimmen, wie eine Datenquelle identifiziert, verwendet und freigegeben wird. Sie können auch Fehlerberichte für eingehende Datendateien aktivieren. To complete the [!UICONTROL Data Source Settings] section:

1. Select a [!UICONTROL Data Source Setting] check box to apply an option to your data source.
2. Klicken Sie auf **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Datenquelleneinstellungen und Menüoptionen](../features/datasources-list-and-settings.md#settings-menu-options)


## Delete a Data Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

Löschen Sie eine Datenquelle, die Sie nicht mehr benötigen.

>[!NOTE]
>
>Bitte beachten Sie die folgenden Einschränkungen:
>
>* You cannot delete an [Active Audience or Data Source Synced Trait](../features/traits/client-activity-synced-audience-traits.md).
>* For customers using Adobe Analytics: Audience Manager does not allow you to delete data sources created automatically from your [!DNL Analytics] report suites. Use the [Core Service](https://marketing.adobe.com/resources/help/en_US/mcloud/) to unmap these data sources.


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. Aktivieren Sie das Kontrollkästchen neben einer oder mehreren Datenquellen.
You can use the [!UICONTROL Search] box to locate the desired data sources if you have a long list.
1. Click  ![](assets/icon_trash.png), then confirm the deletion.
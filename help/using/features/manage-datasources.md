---
description: Um eine neue Datenquelle zu erstellen, gehen Sie zu Zielgruppendaten > Datenquellen > Neu hinzufügen und führen Sie die Schritte für jeden Abschnitt aus, der hier beschrieben wird. Zum Erstellen einer Datenquelle sind Administratorberechtigungen erforderlich.
keywords: Datenquellen;Datenquelle verwalten;Audience Manager-Datenquelle
seo-description: Um eine neue Datenquelle zu erstellen, gehen Sie zu Zielgruppendaten > Datenquellen > Neu hinzufügen und führen Sie die Schritte für jeden Abschnitt aus, der hier beschrieben wird. Zum Erstellen einer Datenquelle sind Administratorberechtigungen erforderlich.
seo-title: Erstellen einer Datenquelle
solution: Audience Manager
title: Data Sources verwalten
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 6%

---

# Konsistentes Verwalten von [!UICONTROL Data Sources] {#manage-data-sources}

## Erstellen Sie eine [!UICONTROL Data Source] {#create-data-source}

Um ein neues [!UICONTROL data source] zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Data Sources > Add New]** und führen Sie die Schritte für jeden Abschnitt aus, der hier beschrieben wird. Zum Erstellen eines [!UICONTROL data source] sind Administratorberechtigungen erforderlich.

<!-- create-datasource.xml -->

>[!TIP]
>
>Beschreibungen dieser verschiedenen Steuerelemente finden Sie unter [Datenquelleneinstellungen und Menüoptionen](../features/datasources-list-and-settings.md#settings-menu-options) .

## [!UICONTROL Data Source] Details {#details}

So schließen Sie den Abschnitt [!UICONTROL Data Source Details] ab:

1. Benennen Sie [!UICONTROL data source].
1. *(Optional)* Beschreiben Sie die  [!UICONTROL data source]. Eine kurze Beschreibung hilft Ihnen bei der Definition der Rolle oder des Zwecks von [!UICONTROL data source].
1. Geben Sie einen [!UICONTROL integration code] an. Im Allgemeinen sind [!UICONTROL integration codes] optional. Sie sind erforderlich, wenn Sie:

   * [Erstellen Sie eine geräteübergreifende Datenquelle](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Verwenden Sie den Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html).[
   * Arbeiten Sie mit [Regeln zur Profilzusammenführung](../features/profile-merge-rules/merge-rules-start.md).

1. Wählen Sie ein **[!UICONTROL ID Type]**. [!UICONTROL ID Type] Zu den Optionen gehören:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Erforderlich zum Erstellen einer  [!UICONTROL Profile Merge Rule]). Beachten Sie bei einigen Kunden, dass diese Auswahl die **[!UICONTROL ID Definition]**-Optionen verfügbar macht.

1. Wählen Sie eine **[!UICONTROL ID Definition]** -Option. Zu den Optionen zählen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Datenexportkontrollen ](../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine  [!UICONTROL data source] und anwenden können  [!UICONTROL destination]. Sie verhindern das Senden von Daten an ein [!UICONTROL destination], wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls] nicht verwenden.

## [!UICONTROL Data Source] Einstellungen {#settings}

Diese Einstellungen bestimmen, wie ein [!UICONTROL data source] identifiziert, verwendet und freigegeben wird. Sie können auch die Fehlerberichterstellung für eingehende Datendateien aktivieren. So schließen Sie den Abschnitt [!UICONTROL Data Source Settings] ab:

1. Aktivieren Sie das Kontrollkästchen [!UICONTROL Data Source Setting] , um eine Option auf [!UICONTROL data source] anzuwenden.
2. Klicken **[!UICONTROL Save]**.

## Datenquelle löschen {#delete-data-source}

<!-- t_datasource_delete.xml -->

Löschen Sie einen [!UICONTROL data source], den Sie nicht mehr benötigen.

>[!NOTE]
>
>Beachten Sie die folgenden Einschränkungen:
>
>* Sie können eine [Aktive Zielgruppe oder Datenquelle synchronisierte Eigenschaft](../features/traits/client-activity-synced-audience-traits.md) nicht löschen.
>* Für Kunden, die Adobe Analytics verwenden: In Audience Manager ist es nicht möglich, automatisch aus Ihren [!DNL Analytics] Report Suites erstellte Datenquellen zu löschen. Verwenden Sie den [Core Service](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html), um die Zuordnung dieser Datenquellen aufzuheben.


1. Klicken **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Aktivieren Sie das Kontrollkästchen neben einer oder mehreren Datenquellen.
Sie können das Feld [!UICONTROL Search] verwenden, um die gewünschten Datenquellen zu finden, wenn Sie über eine lange Liste verfügen.
1. Klicken Sie auf ![](assets/icon_trash.png) und bestätigen Sie dann den Löschvorgang.


>[!MORELIKETHIS]
>
>* [Datenquelleneinstellungen und Menüoptionen](../features/datasources-list-and-settings.md#settings-menu-options)


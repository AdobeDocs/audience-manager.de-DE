---
description: Um eine neue Datenquelle zu erstellen, gehen Sie zu Zielgruppendaten > Datenquellen > Neu hinzufügen und führen Sie die Schritte für jeden Abschnitt aus, der hier beschrieben wird. Zum Erstellen einer Datenquelle sind Administratorberechtigungen erforderlich.
keywords: Datenquellen;Datenquelle verwalten;Audience Manager-Datenquelle
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Data Sources verwalten
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 2%

---

# Konsistentes Verwalten von [!UICONTROL Data Sources] {#manage-data-sources}

## Erstellen Sie eine [!UICONTROL Data Source] {#create-data-source}

So erstellen Sie eine neue [!UICONTROL data source], gehen Sie zu **[!UICONTROL Audience Data > Data Sources > Add New]** und führen Sie die Schritte für jeden Abschnitt aus, der hier beschrieben wird. Administratorberechtigungen sind erforderlich, um eine [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Siehe [Datenquelleneinstellungen und Menüoptionen](../features/datasources-list-and-settings.md#settings-menu-options) für Beschreibungen dieser verschiedenen Steuerelemente.

## [!UICONTROL Data Source] Details {#details}

So schließen Sie die [!UICONTROL Data Source Details] Abschnitt:

1. Benennen Sie die [!UICONTROL data source].
1. *(Optional)* Beschreiben Sie die [!UICONTROL data source]. Eine kurze Beschreibung hilft Ihnen bei der Definition der Rolle oder des Zwecks der [!UICONTROL data source].
1. Stellen Sie eine [!UICONTROL integration code]. Im Allgemeinen [!UICONTROL integration codes] sind optional. Sie sind erforderlich, wenn Sie:

   * [Geräteübergreifende Datenquelle erstellen](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Verwenden Sie die [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Arbeiten mit [Profilzusammenführungsrichtlinien](../features/profile-merge-rules/merge-rules-start.md).

1. Wählen Sie eine **[!UICONTROL ID Type]**. [!UICONTROL ID Type] Zu den Optionen gehören:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Erforderlich zum Erstellen einer [!UICONTROL Profile Merge Rule]). Beachten Sie bei einigen Kunden, dass durch diese Auswahl die **[!UICONTROL ID Definition]** Optionen.

   >[!NOTE]
   >
   >Für jede Organisation, die für Audience Manager und Experience Platform bereitgestellt wird, muss bei der Erstellung einer geräteübergreifenden Datenquelle eine entsprechende [Identitäts-Namespace](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) wird in Experience Platform erstellt.

1. Wählen Sie eine **[!UICONTROL ID Definition]** -Option. Zu den Optionen zählen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Datenexportkontrollen](../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine [!UICONTROL data source] und [!UICONTROL destination]. Sie verhindern das Senden von Daten an eine [!UICONTROL destination] wenn diese Aktion eine Datenschutz- oder Nutzungsvereinbarung verletzt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Einstellungen {#settings}

Diese Einstellungen bestimmen, wie ein [!UICONTROL data source] identifiziert, verwendet und freigegeben wird. Sie können auch die Fehlerberichterstellung für eingehende Datendateien aktivieren. So schließen Sie die [!UICONTROL Data Source Settings] Abschnitt:

1. Wählen Sie eine [!UICONTROL Data Source Setting] Kontrollkästchen zum Anwenden einer Option auf Ihre [!UICONTROL data source].
2. Klicken **[!UICONTROL Save]**.

## Datenquelle löschen {#delete-data-source}

<!-- t_datasource_delete.xml -->

Löschen eines [!UICONTROL data source] die Sie nicht mehr benötigen.

>[!NOTE]
>
>Beachten Sie die folgenden Einschränkungen:
>
>* Eine [Eigenschaften für aktive Zielgruppe oder Datenquelle synchronisiert](../features/traits/client-activity-synced-audience-traits.md).
>* Für Kunden, die Adobe Analytics verwenden: In Audience Manager ist es nicht möglich, automatisch erstellte Datenquellen aus Ihrem [!DNL Analytics] Report Suites. Verwenden Sie die [Hauptdienst](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) , um die Zuordnung dieser Datenquellen aufzuheben.


1. Klicken **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Aktivieren Sie das Kontrollkästchen neben einer oder mehreren Datenquellen.
Sie können die [!UICONTROL Search] , um die gewünschten Datenquellen zu finden, wenn Sie eine lange Liste haben.
1. Klicken  ![](assets/icon_trash.png)und bestätigen Sie dann den Löschvorgang.


>[!MORELIKETHIS]
>
>* [Datenquelleneinstellungen und Menüoptionen](../features/datasources-list-and-settings.md#settings-menu-options)


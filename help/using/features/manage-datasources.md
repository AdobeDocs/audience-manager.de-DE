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
source-wordcount: '372'
ht-degree: 0%

---

# Verwalten von [!UICONTROL Data Sources] {#manage-data-sources}

## Erstellen einer [!UICONTROL Data Source] {#create-data-source}

Um eine neue [!UICONTROL data source] zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Data Sources > Add New]** und führen Sie die Schritte für jeden Abschnitt aus, der hier beschrieben wird. Zum Erstellen eines [!UICONTROL data source] sind Administratorberechtigungen erforderlich.

<!-- create-datasource.xml -->

>[!TIP]
>
>Beschreibungen dieser verschiedenen Steuerelemente finden Sie unter [Data Source Settings and Menu Options](../features/datasources-list-and-settings.md#settings-menu-options) .

## [!UICONTROL Data Source] Details {#details}

So schließen Sie den Abschnitt [!UICONTROL Data Source Details] ab:

1. Nennen Sie die &quot;[!UICONTROL data source]&quot;.
1. *(Optional)* Beschreiben Sie die [!UICONTROL data source]. Eine kurze Beschreibung hilft Ihnen bei der Definition der Rolle oder des Zwecks des [!UICONTROL data source].
1. Geben Sie einen [!UICONTROL integration code] an. Im Allgemeinen ist [!UICONTROL integration codes] optional. Sie sind erforderlich, wenn Sie:

   * [Erstellen Sie eine geräteübergreifende Datenquelle](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Verwenden Sie den [Adobe Experience Platform Identity-Dienst](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Arbeiten mit [Regeln zur Profilzusammenführung](../features/profile-merge-rules/merge-rules-start.md).

1. Wählen Sie eine **[!UICONTROL ID Type]** aus. [!UICONTROL ID Type] -Optionen beinhalten:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Erforderlich zum Erstellen eines [!UICONTROL Profile Merge Rule]). Beachten Sie, dass bei einigen Kunden durch diese Auswahl die **[!UICONTROL ID Definition]** -Optionen verfügbar gemacht werden.

   >[!NOTE]
   >
   >Für jede Organisation, die für Audience Manager und Experience Platform bereitgestellt wird, wird beim Erstellen einer geräteübergreifenden Datenquelle ein entsprechender [Identitäts-Namespace](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) erstellt, auch wenn Sie keine Segmentfreigabe zwischen den beiden Apps eingerichtet haben.

1. Wählen Sie eine **[!UICONTROL ID Definition]** -Option. Zu den Optionen zählen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Datenexportkontrollen](../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine [!UICONTROL data source] und eine [!UICONTROL destination] anwenden können. Sie verhindern, dass Sie Daten an eine [!UICONTROL destination] senden, wenn diese Aktion eine Datenschutz- oder Nutzungsvereinbarung verletzt. Überspringen Sie diesen Abschnitt, wenn Sie nicht [!UICONTROL Data Export Controls] verwenden.

## [!UICONTROL Data Source] Einstellungen {#settings}

Diese Einstellungen bestimmen, wie ein [!UICONTROL data source] identifiziert, verwendet und freigegeben wird. Sie können auch die Fehlerberichterstellung für eingehende Datendateien aktivieren. So schließen Sie den Abschnitt [!UICONTROL Data Source Settings] ab:

1. Aktivieren Sie das Kontrollkästchen [!UICONTROL Data Source Setting] , um eine Option auf Ihren [!UICONTROL data source] anzuwenden.
2. Klicken Sie auf **[!UICONTROL Save]**.

## Data Source löschen {#delete-data-source}

<!-- t_datasource_delete.xml -->

Löschen Sie eine &quot;[!UICONTROL data source]&quot;, die Sie nicht mehr benötigen.

>[!NOTE]
>
>Beachten Sie die folgenden Einschränkungen:
>
>* Sie können eine [aktive Zielgruppe oder eine mit Source synchronisierte Dateneigenschaft](../features/traits/client-activity-synced-audience-traits.md) nicht löschen.
>* Für Kunden, die Adobe Analytics verwenden: Audience Manager erlaubt es nicht, automatisch aus Ihren [!DNL Analytics] Report Suites erstellte Datenquellen zu löschen. Verwenden Sie den [Core Service](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) , um die Zuordnung dieser Datenquellen aufzuheben.

1. Klicken Sie auf **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Aktivieren Sie das Kontrollkästchen neben einer oder mehreren Datenquellen.
Sie können das Feld &quot;[!UICONTROL Search]&quot;verwenden, um die gewünschten Datenquellen zu finden, wenn Sie eine lange Liste haben.
1. Klicken Sie auf ![](assets/icon_trash.png) und bestätigen Sie dann den Löschvorgang.


>[!MORELIKETHIS]
>
>* [Source-Einstellungen und Menüoptionen für Daten](../features/datasources-list-and-settings.md#settings-menu-options)

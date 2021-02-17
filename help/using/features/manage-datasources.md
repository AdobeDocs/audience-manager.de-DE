---
description: Um eine neue Datenquelle zu erstellen, gehen Sie zu "Audience-Daten"> "Datenquellen"> "Hinzufügen Neu"und führen Sie die Schritte für jeden dieser Abschnitte aus. Zum Erstellen einer Datenquelle sind Administratorberechtigungen erforderlich.
keywords: Datenquellen;Datenquelle verwalten;Audience Manager-Datenquelle
seo-description: Um eine neue Datenquelle zu erstellen, gehen Sie zu "Audience-Daten"> "Datenquellen"> "Hinzufügen Neu"und führen Sie die Schritte für jeden dieser Abschnitte aus. Zum Erstellen einer Datenquelle sind Administratorberechtigungen erforderlich.
seo-title: Erstellen einer Datenquelle
solution: Audience Manager
title: Data Sources verwalten
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 5%

---


# Konsistentes Verwalten von [!UICONTROL Data Sources] {#manage-data-sources}

## Erstellen Sie eine [!UICONTROL Data Source] {#create-data-source}

Um ein neues [!UICONTROL data source] zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Data Sources > Add New]** und führen Sie die Schritte für jeden Abschnitt durch, der hier beschrieben wird. Zum Erstellen eines [!UICONTROL data source] sind Administratorberechtigungen erforderlich.

<!-- create-datasource.xml -->

>[!TIP]
>
>Beschreibungen dieser verschiedenen Steuerelemente finden Sie unter [Datenquelleneinstellungen und Menüoptionen](../features/datasources-list-and-settings.md#settings-menu-options).

## [!UICONTROL Data Source] Details {#details}

So füllen Sie den Abschnitt [!UICONTROL Data Source Details] aus:

1. Benennen Sie [!UICONTROL data source].
1. *(Optional)* Beschreiben Sie die  [!UICONTROL data source]. Eine knappe Beschreibung hilft Ihnen, die Rolle oder den Zweck von [!UICONTROL data source] zu definieren.
1. Geben Sie ein [!UICONTROL integration code] an. Im Allgemeinen sind [!UICONTROL integration codes] optional. Sie sind erforderlich, wenn Sie:

   * [Erstellen Sie eine geräteübergreifende Datenquelle](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Verwenden Sie den [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/de-DE/id-service/using/home.html).
   * Arbeiten Sie mit [Profil Merge Rules](../features/profile-merge-rules/merge-rules-start.md).

1. Wählen Sie ein **[!UICONTROL ID Type]**. [!UICONTROL ID Type] umfassen:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Erforderlich, um eine  [!UICONTROL Profile Merge Rule]). Beachten Sie, dass bei einigen Kunden die Optionen **[!UICONTROL ID Definition]** durch diese Auswahl verfügbar sind.

1. Wählen Sie eine Option **[!UICONTROL ID Definition]**. Zu den Optionen zählen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Datenexport-](../features/data-export-controls.md) Steuerelemente sind optionale Classification-Regeln, die Sie auf ein  [!UICONTROL data source] und anwenden können  [!UICONTROL destination]. Sie verhindern, dass Sie Daten an ein [!UICONTROL destination] senden, wenn diese Aktion eine Datenschutz- oder Nutzungsvereinbarung verletzt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls] nicht verwenden.

## [!UICONTROL Data Source] Einstellungen {#settings}

Diese Einstellungen bestimmen, wie ein [!UICONTROL data source] identifiziert, verwendet und freigegeben wird. Sie können auch den Berichte &quot;error&quot;für eingehende Datendateien aktivieren. So füllen Sie den Abschnitt [!UICONTROL Data Source Settings] aus:

1. Aktivieren Sie das Kontrollkästchen [!UICONTROL Data Source Setting], um eine Option auf [!UICONTROL data source] anzuwenden.
2. Klicken **[!UICONTROL Save]**.

## Datenquelle löschen {#delete-data-source}

<!-- t_datasource_delete.xml -->

Löschen Sie ein [!UICONTROL data source], das Sie nicht mehr benötigen.

>[!NOTE]
>
>Beachten Sie die folgenden Einschränkungen:
>
>* Sie können eine [Aktive Audience oder eine Datenquelle synchronisierte Eigenschaft](../features/traits/client-activity-synced-audience-traits.md) nicht löschen.
>* Für Kunden, die Adobe Analytics verwenden: In Audience Manager ist es nicht möglich, automatisch erstellte Datenquellen aus Ihren [!DNL Analytics] Report Suites zu löschen. Verwenden Sie den [Core-Dienst](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html), um die Zuordnung dieser Datenquellen aufzuheben.


1. Klicken **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Aktivieren Sie das Kontrollkästchen neben einer oder mehreren Datenquellen.
Mit dem Feld [!UICONTROL Search] können Sie die gewünschten Datenquellen suchen, wenn Sie eine lange Liste haben.
1. Klicken Sie auf ![](assets/icon_trash.png) und bestätigen Sie dann den Löschvorgang.


>[!MORELIKETHIS]
>
>* [Datenquelleneinstellungen und Menüoptionen](../features/datasources-list-and-settings.md#settings-menu-options)
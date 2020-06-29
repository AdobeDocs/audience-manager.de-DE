---
description: Um eine neue Datenquelle zu erstellen, gehen Sie zu "Audience-Daten"> "Datenquellen"> "Hinzufügen Neu"und führen Sie die Schritte für jeden dieser Abschnitte aus. Zum Erstellen einer Datenquelle sind Administratorberechtigungen erforderlich.
keywords: data sources;manage data source;audience manager data source
seo-description: Um eine neue Datenquelle zu erstellen, gehen Sie zu "Audience-Daten"> "Datenquellen"> "Hinzufügen Neu"und führen Sie die Schritte für jeden dieser Abschnitte aus. Zum Erstellen einer Datenquelle sind Administratorberechtigungen erforderlich.
seo-title: Datenquelle erstellen
solution: Audience Manager
title: Data Sources verwalten
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 2%

---


# Konsistentes Verwalten von [!UICONTROL Data Sources] {#manage-data-sources}

## Erstellen Sie eine [!UICONTROL Data Source] {#create-data-source}

Um eine neue zu erstellen, gehen Sie [!UICONTROL data source]zu den Schritten für die einzelnen Abschnitte, die hier beschrieben werden, **[!UICONTROL Audience Data > Data Sources > Add New]** und führen Sie sie aus. Zum Erstellen einer [!UICONTROL data source]Datei sind Administratorberechtigungen erforderlich.

<!-- create-datasource.xml -->

>[!TIP]
>
>Beschreibungen dieser verschiedenen Steuerelemente finden Sie unter [Datenquelleneinstellungen und Menüoptionen](../features/datasources-list-and-settings.md#settings-menu-options) .

## [!UICONTROL Data Source] Details {#details}

So füllen Sie den [!UICONTROL Data Source Details] Abschnitt aus:

1. Benennen Sie die [!UICONTROL data source].
1. *(Optional)* Beschreiben Sie die [!UICONTROL data source]. Eine knappe Beschreibung hilft Ihnen, die Rolle oder den Zweck der [!UICONTROL data source]Kampagne zu definieren.
1. Geben Sie eine [!UICONTROL integration code]an. Im Allgemeinen [!UICONTROL integration codes] sind sie optional. Sie sind erforderlich, wenn Sie:

   * [Erstellen Sie eine geräteübergreifende Datenquelle](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Verwenden Sie den Identitätsdienst für [Adobe Experience Platformen](https://docs.adobe.com/content/help/en/id-service/using/home.html).
   * Arbeiten mit [Profil Merge Rules](../features/profile-merge-rules/merge-rules-start.md).

1. Wählen Sie eine **[!UICONTROL ID Type]**. [!UICONTROL ID Type] umfassen:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Erforderlich, um eine [!UICONTROL Profile Merge Rule]). Beachten Sie, dass bei einigen Kunden diese Auswahl die **[!UICONTROL ID Definition]** Optionen offen legt.

1. Choose an **[!UICONTROL ID Definition]** option. Zu den Optionen zählen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Data Export Controls](../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf ein [!UICONTROL data source] und anwenden können [!UICONTROL destination]. Sie hindern Sie daran, Daten an eine [!UICONTROL destination] zu senden, wenn diese Aktion eine Datenschutz- oder Nutzungsvereinbarung verletzt. Überspringen Sie diesen Abschnitt, wenn Sie nicht verwenden [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Einstellungen {#settings}

Diese Einstellungen bestimmen, wie ein Element identifiziert, verwendet und freigegeben [!UICONTROL data source] wird. Sie können auch den Berichte &quot;error&quot;für eingehende Datendateien aktivieren. So füllen Sie den [!UICONTROL Data Source Settings] Abschnitt aus:

1. Aktivieren Sie ein [!UICONTROL Data Source Setting] Kontrollkästchen, um eine Option auf Ihre Anwendung anzuwenden [!UICONTROL data source].
2. Klicken **[!UICONTROL Save]**.

## Datenquelle löschen {#delete-data-source}

<!-- t_datasource_delete.xml -->

Löschen Sie eine [!UICONTROL data source] Datei, die Sie nicht mehr benötigen.

>[!NOTE]
>
>Beachten Sie die folgenden Einschränkungen:
>
>* Eine [aktive Audience oder eine Datenquelle-synchronisierte Eigenschaft](../features/traits/client-activity-synced-audience-traits.md)kann nicht gelöscht werden.
>* Für Kunden, die Adobe Analytics verwenden: In Audience Manager ist es nicht möglich, automatisch erstellte Datenquellen aus Ihren [!DNL Analytics] Report Suites zu löschen. Verwenden Sie den [Hauptdienst](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) , um die Zuordnung dieser Datenquellen aufzuheben.


1. Klicken **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Aktivieren Sie das Kontrollkästchen neben einer oder mehreren Datenquellen.
Mit dem [!UICONTROL Search] Feld können Sie die gewünschten Datenquellen suchen, wenn Sie eine lange Liste haben.
1. Klicken Sie auf ![](assets/icon_trash.png)und bestätigen Sie dann den Löschvorgang.


>[!MORELIKETHIS]
>
>* [Datenquelleneinstellungen und Menüoptionen](../features/datasources-list-and-settings.md#settings-menu-options)
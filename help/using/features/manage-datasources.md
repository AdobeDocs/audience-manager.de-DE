---
description: Um eine neue Datenquelle zu erstellen, gehen Sie zu Zielgruppendaten > Datenquellen > Neu hinzufügen und führen Sie die Schritte für jeden hier beschriebenen Abschnitt aus. Zum Erstellen einer Datenquelle sind Administratorberechtigungen erforderlich.
keywords: Datenquellen;Datenquelle verwalten;Audience Manager-Datenquelle
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Verwalten von Datenquellen
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: bda66cb9aaee3a40ae64dda100f42b88696a027e
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---

# Verwalten von [!UICONTROL Data Sources] {#manage-data-sources}

## Erstellen eines [!UICONTROL Data Source] {#create-data-source}

Um ein neues [!UICONTROL data source] zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Data Sources > Add New]** und führen Sie die Schritte für jeden hier beschriebenen Abschnitt aus. Zum Erstellen eines [!UICONTROL data source] sind Administratorberechtigungen erforderlich.

<!-- create-datasource.xml -->

>[!TIP]
>
>Beschreibungen [ verschiedenen Steuerelemente finden Sie unter Einstellungen für Data Source ](../features/datasources-list-and-settings.md#settings-menu-options) Menüoptionen.

## [!UICONTROL Data Source] {#details}

Um den Abschnitt [!UICONTROL Data Source Details] auszufüllen, füllen Sie die folgenden Felder aus:

1. **[!UICONTROL Name]**: Geben Sie einen Namen für die Datenquelle an.
1. **[!UICONTROL Description]** (optional): Geben Sie eine Beschreibung für Ihre Datenquelle ein, um die Rolle oder den Zweck der Datenquelle zu definieren.
1. **[!UICONTROL Integration Code]** (optional): Geben Sie einen Integrations-Code ein. Diese Codes sind erforderlich, wenn Sie Folgendes tun möchten:
   * [Erstellen einer geräteübergreifenden Datenquelle](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Verwenden Sie den [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Arbeiten mit [Profilzusammenführungsregeln](../features/profile-merge-rules/merge-rules-start.md).
1. **[!UICONTROL Namespace]** (schreibgeschützt): Dieses Feld ist schreibgeschützt und wird beim Speichern der Datenquelle automatisch generiert. Wenn Sie Segmente aus dem Audience Manager auf den Experience Platform exportieren möchten, müssen Sie einen entsprechenden [Identitäts-Namespace](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) in Experience Platform erstellen und dabei den automatisch generierten Wert als Namespace ([) ](https://experienceleague.adobe.com/en/docs/experience-platform/identity/features/namespaces#components-of-a-namespace) Experience Platform verwenden.
1. **[!UICONTROL ID Type]**: Wählen Sie den Typ der IDs aus, die diese Datenquelle enthalten soll:
   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (erforderlich zum Erstellen eines [!UICONTROL Profile Merge Rule]). Beachten Sie, dass diese Auswahl für einige Kunden die **[!UICONTROL ID Definition]** Optionen verfügbar macht.
1. Wählen Sie eine **[!UICONTROL ID Definition]**. Zu den Optionen zählen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Datenexportsteuerelemente](../features/data-export-controls.md) sind optionale Klassifizierungsregeln, die Sie auf eine [!UICONTROL data source] und [!UICONTROL destination] anwenden können. Sie verhindern, dass Sie Daten an einen [!UICONTROL destination] senden, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls] nicht verwenden.

## [!UICONTROL Data Source] {#settings}

Diese Einstellungen bestimmen, wie ein [!UICONTROL data source] identifiziert, verwendet und freigegeben wird. Sie können auch die Fehlerberichterstattung für eingehende Datendateien aktivieren. So schließen Sie den Abschnitt [!UICONTROL Data Source Settings] ab:

1. Aktivieren Sie ein [!UICONTROL Data Source Setting] Kontrollkästchen, um eine Option auf Ihre [!UICONTROL data source] anzuwenden.
2. Klicken Sie auf **[!UICONTROL Save]**.

## Löschen eines Daten-Source {#delete-data-source}

<!-- t_datasource_delete.xml -->

Löschen Sie eine [!UICONTROL data source], die Sie nicht mehr benötigen.

>[!NOTE]
>
>Bitte beachten Sie die folgenden Einschränkungen:
>
>* Sie können keine [Active Audience oder synchronisierte Data Source-Eigenschaft](../features/traits/client-activity-synced-audience-traits.md) löschen.
>* Für Kunden, die Adobe Analytics verwenden: Audience Manager erlaubt es Ihnen nicht, automatisch erstellte Datenquellen aus Ihren [!DNL Analytics] Report Suites zu löschen. Mit dem [Core Service](https://experienceleague.adobe.com/en/docs/core-services/interface/services/customer-attributes/attributes) können Sie die Zuordnung dieser Datenquellen aufheben.

1. Klicken Sie auf **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Aktivieren Sie das Kontrollkästchen neben einer oder mehreren Datenquellen.
Sie können das [!UICONTROL Search] verwenden, um die gewünschten Datenquellen zu finden, wenn Sie über eine lange Liste verfügen.
1. Klicken Sie auf ![](assets/icon_trash.png) und bestätigen Sie dann den Löschvorgang.


>[!MORELIKETHIS]
>
>* [Einstellungen und Menüoptionen in Data Source](../features/datasources-list-and-settings.md#settings-menu-options)

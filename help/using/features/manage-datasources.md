---
description: Um eine neue Datenquelle zu erstellen, gehen Sie zu Zielgruppendaten > Datenquellen > Neu hinzufügen und führen Sie die Schritte für jeden Abschnitt durch, der hier beschrieben wird. Zum Erstellen einer Datenquelle sind Administratorberechtigungen erforderlich.
keywords: Datenquellen;Datenquelle verwalten;Zielgruppen-Manager-Datenquelle
seo-description: Um eine neue Datenquelle zu erstellen, gehen Sie zu Zielgruppendaten > Datenquellen > Neu hinzufügen und führen Sie die Schritte für jeden Abschnitt durch, der hier beschrieben wird. Zum Erstellen einer Datenquelle sind Administratorberechtigungen erforderlich.
seo-title: Datenquelle erstellen
solution: Audience Manager
title: Data Sources verwalten
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Manage Data Sources {#manage-data-sources}

## Create a Data Source {#create-data-source}

Um eine neue Datenquelle zu erstellen, gehen Sie zu den Schritten für jeden Abschnitt, der hier beschrieben wird, **[!UICONTROL Audience Data > Data Sources > Add New]** und führen Sie sie aus. Zum Erstellen einer Datenquelle sind Administratorberechtigungen erforderlich.

<!-- create-datasource.xml -->

>[!TIP]
>
>Beschreibungen dieser verschiedenen Steuerelemente finden Sie unter [Datenquelleneinstellungen und Menüoptionen](../features/datasources-list-and-settings.md#settings-menu-options) .

## Datenquellendetails {#details}

So füllen Sie den [!UICONTROL Data Source Details] Abschnitt aus:

1. Benennen Sie die Datenquelle.
1. *(Optional)* Beschreiben Sie die Datenquelle. Eine kurze Beschreibung hilft Ihnen, die Rolle oder den Zweck der Datenquelle zu definieren.
1. Geben Sie einen Integrationscode ein. Im Allgemeinen sind Integrationscodes optional. Sie sind erforderlich, wenn Sie:

   * [Erstellen Sie eine geräteübergreifende Datenquelle](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Verwenden Sie den [Experience Cloud ID-Dienst](https://marketing.adobe.com/resources/help/en_US/mcvid/).
   * Arbeiten Sie mit [Regeln](../features/profile-merge-rules/merge-rules-start.md)zum Profilzusammenführen.

1. Wählen Sie eine **[!UICONTROL ID Type]**. Zu den ID-Typ-Optionen zählen:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Erforderlich, um eine [!UICONTROL Profile Merge Rule]). Beachten Sie, dass bei einigen Kunden diese Auswahl die **[!UICONTROL ID Definition]** Optionen offen legt.

1. Choose an **[!UICONTROL ID Definition]** option. Zu den Optionen zählen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Datenexportkontrolle {#export-controls}

[Data Export Controls](../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine Datenquelle und ein Ziel anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie nicht verwenden [!UICONTROL Data Export Controls].

## Data Source Settings {#settings}

Diese Einstellungen bestimmen, wie eine Datenquelle identifiziert, verwendet und freigegeben wird. Sie können auch die Fehlermeldung für eingehende Datendateien aktivieren. So füllen Sie den [!UICONTROL Data Source Settings] Abschnitt aus:

1. Aktivieren Sie ein [!UICONTROL Data Source Setting] Kontrollkästchen, um eine Option auf Ihre Datenquelle anzuwenden.
2. Klicken Sie auf **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Datenquelleneinstellungen und Menüoptionen](../features/datasources-list-and-settings.md#settings-menu-options)


## Datenquelle löschen {#delete-data-source}

<!-- t_datasource_delete.xml -->

Löschen Sie eine Datenquelle, die Sie nicht mehr benötigen.

>[!NOTE]
>
>Beachten Sie die folgenden Einschränkungen:
>
>* Sie können keine [Active Audience- oder Datenquelle-synchronisierten Eigenschaften](../features/traits/client-activity-synced-audience-traits.md)löschen.
>* Für Kunden, die Adobe Analytics verwenden: Audience Manager erlaubt Ihnen nicht, automatisch erstellte Datenquellen aus Ihren [!DNL Analytics] Report Suites zu löschen. Verwenden Sie den [Hauptdienst](https://marketing.adobe.com/resources/help/en_US/mcloud/) , um die Zuordnung dieser Datenquellen aufzuheben.


1. Click **[!UICONTROL Audience Data]** &gt; **[!UICONTROL Data Sources]**.
1. Aktivieren Sie das Kontrollkästchen neben einer oder mehreren Datenquellen.
Mit dem [!UICONTROL Search] Feld können Sie die gewünschten Datenquellen suchen, wenn Sie eine lange Liste haben.
1. Klicken Sie auf ![](assets/icon_trash.png)und bestätigen Sie dann den Löschvorgang.
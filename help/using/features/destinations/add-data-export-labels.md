---
description: Datenexportbeschriftungen funktionieren mit den Exportkontrollen, die Sie in einer Datenquelle festlegen. Mit Datenexportbeschriftungen können Sie einem Segment keine eingeschränkten Eigenschaften hinzufügen und keine Segmentdaten an ein Ziel senden. Sie können mehrere Exportbezeichnungen auf ein neues oder vorhandenes Cookie- oder URL-Ziel setzen.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: Hinzufügen von Datenexportkontrollen zu einem Ziel
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# Hinzufügen von Datenexportbeschriftungen zu einem Ziel {#add-data-export-labels}

[!DNL Data Export Labels] arbeitet mit dem [!DNL Export Controls], den Sie in einer Datenquelle festlegen. [!DNL Data Export Labels] verhindert, dass Sie eingeschränkte Eigenschaften zu einem Segment hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Exportbezeichnungen auf ein neues oder vorhandenes [!DNL cookie] - oder [!DNL URL] -Ziel festlegen.

>[!NOTE]
>
>Um eine Exportbeschriftung hinzuzufügen, benötigen Sie Administratorberechtigungen *oder*, die ausreichen, um ein Ziel zu erstellen oder zu bearbeiten.

<!-- t_export_labels.xml -->

So fügen Sie einem Ziel Exportbezeichnungen hinzu:

1. Klicken Sie auf **[!UICONTROL Audience Data]**:
   * Für neue Ziele: Klicken Sie auf **[!UICONTROL Create New Destination]**. Füllen Sie den Abschnitt [!UICONTROL Basic Information] aus, bevor Sie eine Datenexportbeschriftung auswählen. Weitere Informationen finden Sie unter [Erstellen eines Cookie-Ziels](../../features/destinations/create-cookie-destination.md) oder [Erstellen eines URL-Ziels](../../features/destinations/create-url-destination.md) .
   * Für vorhandene Ziele: Verwenden Sie das Feld [!DNL Search] , um Ihr Ziel zu finden, oder scrollen Sie durch die Liste und klicken Sie auf den Zielnamen, um es zu öffnen.
1. Wählen Sie einen [!DNL Data Export Label] aus. Lassen Sie die Kontrollkästchen leer, wenn Sie keine Exportbeschränkungen festlegen möchten. Exportbezeichnungen umfassen die folgenden Optionen:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Exportbeschränkungen funktionieren nur, wenn Sie eine [passende Exportsteuerung](../../features/data-export-controls.md) für eine Datenquelle festlegen.
1. Klicken Sie auf **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Erstellen einer Datenquelle](../../features/manage-datasources.md#create-data-source)

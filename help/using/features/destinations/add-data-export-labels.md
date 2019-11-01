---
description: Datenexportbeschriftungen funktionieren mit den Exportsteuerelementen, die Sie in einer Datenquelle festlegen. Datenexportbeschriftungen verhindern, dass Sie eingeschränkte Eigenschaften zu einem Segment hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Exportbeschriftungen für ein neues oder vorhandenes Cookie- oder URL-Ziel festlegen.
seo-description: Datenexportbeschriftungen funktionieren mit den Exportsteuerelementen, die Sie in einer Datenquelle festlegen. Datenexportbeschriftungen verhindern, dass Sie eingeschränkte Eigenschaften zu einem Segment hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Exportbeschriftungen für ein neues oder vorhandenes Cookie- oder URL-Ziel festlegen.
seo-title: Hinzufügen von Datenexportsteuerelementen zu einem Ziel
solution: Audience Manager
title: Hinzufügen von Datenexportsteuerelementen zu einem Ziel
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---



# Hinzufügen von Datenexport-Bezeichnungen zu einem Ziel {#add-data-export-labels}

[!DNL Data Export Labels] mit der [!DNL Export Controls] festgelegten Datenquelle arbeiten. [!DNL Data Export Labels] verhindern, dass Sie eingeschränkte Eigenschaften zu einem Segment hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Exportbeschriftungen für ein neues oder vorhandenes [!DNL cookie] oder [!DNL URL] Ziel festlegen.

>[!NOTE]
>
>Um eine Exportbeschriftung hinzuzufügen, benötigen Sie Administratorberechtigungen *oder* ausreichende Berechtigungen, um ein Ziel zu erstellen oder zu bearbeiten.

<!-- t_export_labels.xml -->

So fügen Sie einem Ziel Exportbeschriftungen hinzu:

1. Klicken Sie auf **[!UICONTROL Audience Data]**:
   * Für neue Ziele: Klicken Sie auf **[!UICONTROL Create New Destination]**. Füllen Sie den [!UICONTROL Basic Information] Abschnitt aus, bevor Sie eine Datenexportbeschriftung auswählen. Weitere Informationen finden Sie unter [Erstellen eines Cookie-Ziels](../../features/destinations/create-cookie-destination.md) oder [Erstellen eines URL-Ziels](../../features/destinations/create-url-destination.md) .
   * Für bestehende Ziele: Verwenden Sie das [!DNL Search] Feld, um Ihr Ziel zu finden, oder blättern Sie durch die Liste und klicken Sie auf den Zielnamen, um es zu öffnen.
1. Wählen Sie eine [!DNL Data Export Label]. Lassen Sie die Kontrollkästchen leer, wenn Sie keine Exportbeschränkungen festlegen möchten. Exportbeschriftungen umfassen die folgenden Optionen:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Exportbeschränkungen funktionieren nur, wenn Sie eine [übereinstimmende Exportkontrolle](../../features/data-export-controls.md) für eine Datenquelle festlegen.
1. Klicken Sie auf **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Datenquelle erstellen](../../features/manage-datasources.md#create-data-source)
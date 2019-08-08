---
description: Datenexportbeschriftungen funktionieren mit den Exportsteuerelementen, die Sie in einer Datenquelle festgelegt haben. Datenexportbeschriftungen verhindern, dass Sie einem Segment eingeschränkte Eigenschaften hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Beschriftungen auf ein neues oder vorhandenes Cookie oder ein URL-Ziel festlegen.
seo-description: Datenexportbeschriftungen funktionieren mit den Exportsteuerelementen, die Sie in einer Datenquelle festgelegt haben. Datenexportbeschriftungen verhindern, dass Sie einem Segment eingeschränkte Eigenschaften hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Beschriftungen auf ein neues oder vorhandenes Cookie oder ein URL-Ziel festlegen.
seo-title: Datenexport-Steuerelemente zu einem Ziel hinzufügen
solution: Audience Manager
title: Datenexport-Steuerelemente zu einem Ziel hinzufügen
translation-type: tm+mt
source-git-commit: 6e2b5842ad3ca52f7ed0fb72231deb6fa614b70b

---



# Datenexport-Beschriftungen zu einem Ziel hinzufügen {#add-data-export-labels}

[!DNL Data Export Labels] mit den [!DNL Export Controls] in einer Datenquelle festgelegten Arbeiten. [!DNL Data Export Labels] verhindern, dass Sie einem Segment eingeschränkte Eigenschaften hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Beschriftungen auf ein neues oder ein vorhandenes [!DNL cookie] oder [!DNL URL] ein Ziel festlegen.

>[!NOTE]
>
>Um eine Exportbeschriftung hinzuzufügen, benötigen Sie Administratorrechte *oder* ausreichende Rechte, um ein Ziel zu erstellen oder zu bearbeiten.

<!-- t_export_labels.xml -->

So fügen Sie einem Ziel eine Exportbeschriftung hinzu:

1. Klicken Sie auf **[!UICONTROL Audience Data]**:
   * Für neue Ziele: Klicken **[!UICONTROL Create New Destination]** Sie auf. Füllen Sie den [!UICONTROL Basic Information] Abschnitt aus, bevor Sie eine Datenexportbeschriftung auswählen. Weitere Informationen finden Sie unter [Erstellen eines Cookie-Ziels](../../features/destinations/manage-destinations.md#create-cookie-destination) oder [Erstellen eines URL-Ziels](../../features/destinations/manage-destinations.md#configure-url-destination) .
   * Für vorhandene Ziele: Verwenden Sie das [!DNL Search] Kästchen, um Ihr Ziel zu finden, oder klicken Sie auf den Zielnamen, um ihn zu öffnen.
1. Wählen Sie eine [!DNL Data Export Label]. Lassen Sie die Kontrollkästchen leer, wenn Sie keine Exportbeschränkungen festlegen möchten. Zu den Exportbeschriftungen zählen die folgenden Optionen:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Exporteinschränkungen funktionieren nur, wenn Sie ein [passendes Exportsteuerelement](../../features/data-export-controls.md) für eine Datenquelle festlegen.
1. Klicken Sie auf **[!UICONTROL Save]**.

>[!MORE_ LIKE_ THIS]
>
>* [Datenquelle erstellen](../../features/manage-datasources.md#create-data-source)
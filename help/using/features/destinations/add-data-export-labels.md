---
description: Datenexportbeschriftungen funktionieren mit den Exportsteuerelementen, die Sie in einer Datenquelle festlegen. Datenexport-Bezeichnungen verhindern, dass Sie eingeschränkte Eigenschaften zu einem Segment hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Exportbeschriftungen für ein neues oder vorhandenes Cookie- oder URL-Ziel festlegen.
seo-description: Datenexportbeschriftungen funktionieren mit den Exportsteuerelementen, die Sie in einer Datenquelle festlegen. Datenexport-Bezeichnungen verhindern, dass Sie eingeschränkte Eigenschaften zu einem Segment hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Exportbeschriftungen für ein neues oder vorhandenes Cookie- oder URL-Ziel festlegen.
seo-title: Hinzufügen von Datenexportkontrollen zu einem Ziel
solution: Audience Manager
title: Hinzufügen von Datenexportkontrollen zu einem Ziel
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 7%

---



# hinzufügen Datenexportbeschriftungen an ein Ziel {#add-data-export-labels}

[!DNL Data Export Labels] mit der  [!DNL Export Controls] festgelegten Datenquelle arbeiten. [!DNL Data Export Labels] verhindern, dass Sie eingeschränkte Eigenschaften zu einem Segment hinzufügen und Segmentdaten an ein Ziel senden. Sie können mehrere Exportbezeichnungen auf ein neues oder vorhandenes [!DNL cookie]- oder [!DNL URL]-Ziel festlegen.

>[!NOTE]
>
>Um eine Exportbeschriftung hinzuzufügen, benötigen Sie Administratorberechtigungen *oder*, die ausreichen, um ein Ziel zu erstellen oder zu bearbeiten.

<!-- t_export_labels.xml -->

So fügen Sie einem Ziel Exportbeschriftungen hinzu:

1. Klicken **[!UICONTROL Audience Data]**:
   * Für neue Ziele: Klicken Sie auf **[!UICONTROL Create New Destination]**. Füllen Sie den Abschnitt [!UICONTROL Basic Information] aus, bevor Sie eine Datenexportbeschriftung auswählen. Weitere Informationen finden Sie unter [Erstellen eines Cookie-Ziels](../../features/destinations/create-cookie-destination.md) oder [Erstellen eines URL-Ziels](../../features/destinations/create-url-destination.md).
   * Für bestehende Ziele: Verwenden Sie das Feld [!DNL Search], um Ihr Ziel zu finden, oder blättern Sie durch die Liste und klicken Sie auf den Zielnamen, um es zu öffnen.
1. Wählen Sie eine [!DNL Data Export Label]. Lassen Sie die Kontrollkästchen leer, wenn Sie keine Exportbeschränkungen festlegen möchten. Exportbeschriftungen umfassen die folgenden Optionen:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >Exportbeschränkungen funktionieren nur, wenn Sie eine [übereinstimmende Exportsteuerung](../../features/data-export-controls.md) für eine Datenquelle festlegen.
1. Klicken **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Erstellen einer Datenquelle](../../features/manage-datasources.md#create-data-source)
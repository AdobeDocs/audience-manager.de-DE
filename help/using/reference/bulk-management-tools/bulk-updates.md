---
description: Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften, Modelle, Datenquellen und Segment- oder Trait-Ordnerelemente in einem einzigen Vorgang bearbeiten. Befolgen Sie diese Anweisungen, um Massenaktualisierungen durchzuführen.
keywords: Baaam
seo-description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: Massenaktualisierungen
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
TQID: https://experienceleague.adobe.com/fDSvlPqWTgaw-SszCIa5M2qxJcyfrewPaW03eVShhDw
product_v2:
  - id: df80eeb1-8d72-467e-b0df-9d51c7d3a0a1
feature_v2:
  - id: baaa0dd2-d27e-4921-aae3-7888623a5fa5
  - id: ce14ba14-a06d-4b2b-b7dd-04cb862494ec
subfeature_v2:
  - id: c2c33729-f309-4bc2-92ba-87c475259df3
  - id: d3dfac44-e20d-492d-a806-0f4a4a495901
  - id: fa77d762-7e75-47b2-9bb4-e3fcf50d251d
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 395823e4876ddac1f56af10a1b110b60ff6f88a4
workflow-type: tm+mt
source-wordcount: 268
ht-degree: 0%

---

# Massenaktualisierungen{#bulk-updates}

Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften, Modelle, Datenquellen und Segment- oder Trait-Ordnerelemente in einem einzigen Vorgang bearbeiten. Befolgen Sie diese Anweisungen, um Massenaktualisierungen durchzuführen.

>[!IMPORTANT]
>
>Die Tools für die Massenverwaltung sind kein offiziell unterstütztes Adobe-Angebot. Die Fehlerbehebung und der Support über die Kundenunterstützung werden von Fall zu Fall durchgeführt.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md), die in der [!DNL Audience Manager]-Benutzeroberfläche zugewiesen sind, werden in der [!UICONTROL Bulk Management Tools] berücksichtigt.

Um Massenaktualisierungen vorzunehmen, öffnen Sie das [!UICONTROL Bulk Management Tools] Arbeitsblatt und:

1. Klicken Sie auf die Registerkarte **[!UICONTROL Headers]** und kopieren Sie die Aktualisierungskopfzeilen für das Element, das Sie bearbeiten möchten.
2. Klicken Sie auf die Registerkarte **[!UICONTROL Update]** .
3. Fügen Sie die Aktualisierungskopfzeilen in die erste Zeile des Aktualisierungsarbeitsblatts ein. Beachten Sie Folgendes:

   * Beim Aktualisieren eines Ordners sind alle Kopfzeilen erforderlich.
   * Beim Aktualisieren von Segmenten oder Eigenschaften benötigen Sie nur die Segment-ID (SID) und das Header-Element, das geändert werden muss. Löschen Sie nicht verwendete Header.

4. Fügen Sie die Daten, die Sie ändern möchten, ein, oder geben Sie sie anhand der Kopfzeilenbeschriftung in eine entsprechende Spalte ein.
5. Klicken Sie in der Symbolleiste des Arbeitsblatts auf eine Aktualisierungsschaltfläche, die der        Element, das Sie aktualisieren.
Diese Aktion öffnet das Dialogfeld [!UICONTROL Account Information].

6. Geben Sie die erforderlichen [Anmeldeinformationen“ ein &#x200B;](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) klicken Sie auf **[!UICONTROL Submit]**.

   Das Arbeitsblatt erstellt eine [!UICONTROL Results]. Die Spalte [!UICONTROL Results] gibt die JSON-Antwort für einen erfolgreichen Vorgang zurück. Beispiele finden Sie in [REST](../../api/rest-api-main/rest-api-main.md)APIs). Vor der Dateneingabe sollte Ihr Massenaktualisierungsarbeitsblatt wie folgt aussehen:

![](assets/update.png)

Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Tools für die Massenverwaltung](../../reference/bulk-management-tools/bulk-troubleshooting.md).

---
description: Mit der Massenerstellung können Sie mehrere Datenquellen, abgeleitete Signale, Segmente, Eigenschaften und andere Elemente mit einem einzigen Vorgang erstellen. Befolgen Sie diese Anweisungen, um eine Massenerstellungsanfrage zu stellen.
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: Massen-Erstellung
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
TQID: https://experienceleague.adobe.com/EbavgrTOfC5Wjx4IwGxt4Gi3-d-EkOSQjG3WaRAionU
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
source-wordcount: 288
ht-degree: 0%

---

# Massen-Erstellung{#bulk-create}

Mit der Massenerstellung können Sie mehrere Datenquellen, abgeleitete Signale, Segmente, Eigenschaften und andere Elemente mit einem einzigen Vorgang erstellen. Befolgen Sie diese Anweisungen, um eine Massenerstellungsanfrage zu stellen.

>[!IMPORTANT]
>
>Die Tools für die Massenverwaltung sind kein offiziell unterstütztes Adobe-Angebot. Die Fehlerbehebung und der Support über die Kundenunterstützung werden von Fall zu Fall durchgeführt.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md), die in der [!DNL Audience Manager]-Benutzeroberfläche zugewiesen sind, werden in der [!UICONTROL Bulk Management Tools] berücksichtigt.

>[!CAUTION]
>
>Mischen Sie in einer Massenerstellungsanfrage keine Objekttypen. Die Kopfzeilen für jedes Objekt sind eindeutig und können nicht kombiniert werden. Löschen Sie das Arbeitsblatt und stellen Sie eine separate Anfrage für verschiedene Elemente.

Um Objekte stapelweise zu erstellen, öffnen Sie das [!UICONTROL Bulk Management Tools] Arbeitsblatt und:

1. Klicken Sie auf die Registerkarte **[!UICONTROL Headers]** und kopieren Sie die Kopfzeilen für das Element, das Sie hinzufügen möchten.
2. Klicken Sie auf die Registerkarte **[!UICONTROL Create]** .
3. Fügen Sie die Create-Kopfzeilen in die erste Zeile des Aktualisierungsarbeitsblatts ein.
4. Fügen Sie die Daten, die Sie ändern möchten, ein, oder geben Sie sie anhand der Kopfzeilenbeschriftung in eine entsprechende Spalte ein.
5. Klicken Sie in der Symbolleiste des Arbeitsblatts auf die Schaltfläche Erstellen , die dem zu aktualisierenden Element entspricht.
Diese Aktion öffnet das Dialogfeld [!UICONTROL Account Information].
6. Geben Sie die erforderlichen [Anmeldeinformationen“ ein &#x200B;](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) klicken Sie auf **[!UICONTROL Submit]**.

Das Arbeitsblatt erstellt eine [!UICONTROL Results]. Die Spalte [!UICONTROL Results] gibt die JSON-Antwort für einen erfolgreichen Vorgang zurück. Beispiele finden Sie in [REST](../../api/rest-api-main/rest-api-main.md)APIs). Bevor Sie Daten eingeben, sollte Ihr Arbeitsblatt für die Massenerstellung dem folgenden Beispiel ähneln. Beachten Sie, dass alle verschiedenen Erstellungsoptionen hier nicht angezeigt werden. Dies ist enthalten, damit Sie besser verstehen, wie ein ausgefülltes Arbeitsblatt aussehen könnte.

![](assets/cretetraits.png)

Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Tools für die Massenverwaltung](../../reference/bulk-management-tools/bulk-troubleshooting.md).

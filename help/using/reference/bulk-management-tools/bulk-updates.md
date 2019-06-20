---
description: Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften und Segmente oder Eigenschaftenordner in einem einzelnen Vorgang bearbeiten. Führen Sie die folgenden Schritte aus, um Massenaktualisierungen vorzunehmen.
keywords: baaam
seo-description: Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften und Segmente oder Eigenschaftenordner in einem einzelnen Vorgang bearbeiten. Führen Sie die folgenden Schritte aus, um Massenaktualisierungen vorzunehmen.
seo-title: Massenaktualisierungen
solution: Audience Manager
title: Massenaktualisierungen
uuid: 22 f 1 badd-a 274-4 d 3 e -9957-a 24 bf 8 c 1 d 0 dc
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Massenaktualisierungen{#bulk-updates}

Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften und Segmente oder Eigenschaftenordner in einem einzelnen Vorgang bearbeiten. Führen Sie die folgenden Schritte aus, um Massenaktualisierungen vorzunehmen.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>Die Variable [!UICONTROL Bulk Management Tools]*wird nicht* unterstützt [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. Für Massenänderungen wird empfohlen, stattdessen mit den [Audience Manager-apis](../../api/rest-api-main/aam-api-getting-started.md) zu arbeiten. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

Um Massenaktualisierungen vorzunehmen, öffnen Sie das [!UICONTROL Bulk Management Tools] Arbeitsblatt und:

1. Klicken Sie auf die **[!UICONTROL Headers]** Registerkarte und kopieren Sie die Aktualisierungskopfzeilen für das Element, das Sie bearbeiten möchten.
1. Klicken Sie auf die **[!UICONTROL Update]** Registerkarte.
1. Fügen Sie die Updatepakete in die erste Zeile des Aktualisierungsarbeitsblatts ein. Beachten Sie Folgendes:

   * Beim Aktualisieren eines Ordners sind alle Header erforderlich.
   * Beim Aktualisieren von Segmenten oder Eigenschaften benötigen Sie lediglich die Segment-ID (SID) und das Header-Element, das geändert werden muss. Löschen Sie nicht verwendete Header.

1. Fügen Sie die Daten, die Sie ändern möchten, in eine entsprechende Spalte ein, basierend auf der Kopfzeilenbeschriftung.
1. Klicken Sie in der Symbolleiste des Arbeitsblatts auf eine Aktualisierungsschaltfläche, die dem Element entspricht, das Sie aktualisieren.
Mit dieser Aktion wird das [!UICONTROL Account Information] Dialogfeld geöffnet.

1. Geben Sie die erforderlichen [Informationen ein](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) und klicken **[!UICONTROL Submit]** Sie auf.

   Das Arbeitsblatt erstellt eine [!UICONTROL Results] Spalte. Die [!UICONTROL Results] Spalte gibt die JSON-Antwort für einen erfolgreichen Vorgang zurück. Beispiele finden Sie in [den REST-apis](../../api/rest-api-main/rest-api-main.md) . Vor der Eingabe der Daten sollte Ihr Massen-Updatesheet wie folgt aussehen:

![](assets/update.png)

Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden [Sie weitere Informationen unter Fehlerbehebung für Massenverwaltungswerkzeuge](../../reference/bulk-management-tools/bulk-troubleshooting.md).

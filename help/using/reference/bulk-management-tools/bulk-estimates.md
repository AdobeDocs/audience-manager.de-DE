---
description: Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Führen Sie die folgenden Schritte aus, um eine Massenschätzung anzufordern.
seo-description: Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Führen Sie die folgenden Schritte aus, um eine Massenschätzung anzufordern.
seo-title: Massenschätzungen
solution: Audience Manager
title: Massenschätzungen
uuid: 63 b 2 f 06 a -8 ba 0-47 a 2-bd 0 b -8039 b 2 d 4 c 95 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Massenschätzungen{#bulk-estimates}

Eine Massenschätzung gibt Daten zur Segmentgröße basierend auf Segmentregeln zurück. Führen Sie die folgenden Schritte aus, um eine Massenschätzung anzufordern.

<!-- 

t_bulk_estimates.xml

 -->

>[!NOTE]
>
>Die Variable [!UICONTROL Bulk Management Tools]*wird nicht* unterstützt [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. Für Massenänderungen wird empfohlen, stattdessen mit den [Audience Manager-apis](../../api/rest-api-main/aam-api-getting-started.md) zu arbeiten. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

Um Massenaktualisierungen vorzunehmen, öffnen Sie das [!UICONTROL Bulk Management Tools] Arbeitsblatt und:

1. Klicken Sie auf die **[!UICONTROL Headers]** Registerkarte und kopieren Sie die [!UICONTROL Estimate Segment Size] Kopfzeile.
1. Klicken Sie auf die **[!UICONTROL Estimate]** Registerkarte.
1. Fügen Sie die Schätzung in die erste Zeile des Schätzarbeitsblatts ein.
1. Fügen Sie die Daten, die Sie ändern möchten, in eine entsprechende Spalte ein, basierend auf der Kopfzeilenbeschriftung.
1. Klicken Sie in der Symbolleiste des Arbeitsblatts auf die Schaltfläche Erstellen, die mit dem Element übereinstimmt, das Sie aktualisieren.
Mit dieser Aktion wird das [!UICONTROL Account Information] Dialogfeld geöffnet.

1. Geben Sie die erforderlichen [Informationen ein](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) und klicken **[!UICONTROL Submit]** Sie auf.

Diese Aktion erstellt eine [!UICONTROL Response] Spalte im Arbeitsblatt mit geschätzten Segmentgrößendaten. Bevor Sie Daten eingeben, sollte Ihr Arbeitsblatt zur Massenschätzung wie folgt aussehen:

![](assets/estimate.png)Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden [Sie weitere Informationen unter Fehlerbehebung für Massenverwaltungswerkzeuge](../../reference/bulk-management-tools/bulk-troubleshooting.md).


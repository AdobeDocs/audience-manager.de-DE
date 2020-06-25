---
description: Mit der Massenerstellung können Sie mehrere Datenquellen, abgeleitete Signale, Segmente, Eigenschaften und andere Elemente mit einem einzigen Vorgang erstellen. Befolgen Sie diese Anweisungen, um eine Anforderung zur Massenerstellung zu erstellen.
seo-description: Mit der Massenerstellung können Sie mehrere Datenquellen, abgeleitete Signale, Segmente, Eigenschaften und andere Elemente mit einem einzigen Vorgang erstellen. Befolgen Sie diese Anweisungen, um eine Anforderung zur Massenerstellung zu erstellen.
seo-title: Massenanfertigung
solution: Audience Manager
title: Massenanfertigung
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: baaam
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 0%

---


# Massenanfertigung{#bulk-create}

Mit der Massenerstellung können Sie mehrere Datenquellen, abgeleitete Signale, Segmente, Eigenschaften und andere Elemente mit einem einzigen Vorgang erstellen. Befolgen Sie diese Anweisungen, um eine Anforderung zur Massenerstellung zu erstellen.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[In der Benutzeroberfläche zugewiesene RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) werden berücksichtigt [!DNL Audience Manager] [!UICONTROL Bulk Management Tools].

>[!CAUTION]
>
>Mischen Sie keine Objekttypen in einer Massenerstellungsanforderung. Die Kopfzeilen für die einzelnen Objekte sind eindeutig und können nicht kombiniert werden. Löschen Sie das Arbeitsblatt und stellen Sie eine separate Anforderung für verschiedene Elemente ein.

Um Objekte stapelweise zu erstellen, öffnen Sie das [!UICONTROL Bulk Management Tools] Arbeitsblatt und:

1. Klicken Sie auf die **[!UICONTROL Headers]** Registerkarte und kopieren Sie die Kopfzeilen für das Element, das Sie hinzufügen möchten.
2. Click the **[!UICONTROL Create]** tab.
3. Fügen Sie die Überschriften zum Erstellen in die erste Zeile des Aktualisierungsarbeitsblatts ein.
4. Fügen Sie die Daten, die Sie ändern möchten, basierend auf der Kopfzeilenbeschriftung in eine entsprechende Spalte ein oder geben Sie sie ein.
5. Klicken Sie in der Symbolleiste des Arbeitsblatts auf die Schaltfläche Erstellen, die dem zu aktualisierenden Element entspricht.
Diese Aktion öffnet das [!UICONTROL Account Information] Dialogfeld.
6. Geben Sie die erforderlichen [Anmeldedaten](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ein und klicken Sie auf **[!UICONTROL Submit]**.

Das Arbeitsblatt erstellt eine [!UICONTROL Results] Spalte. Die [!UICONTROL Results] Spalte gibt die JSON-Antwort für einen erfolgreichen Vorgang zurück. Beispiele finden Sie in den [REST-APIs](../../api/rest-api-main/rest-api-main.md) . Bevor Sie Daten eingeben, sollte das Arbeitsblatt zur Massenerstellung dem folgenden Beispiel ähneln. Beachten Sie, dass hier nicht alle verschiedenen Erstellungsoptionen angezeigt werden. Diese Funktion hilft Ihnen, zu verstehen, wie ein ausgefülltes Arbeitsblatt aussehen könnte.

![](assets/cretetraits.png)

Wenn Ihr Massenupdate einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Massenverwaltungstools](../../reference/bulk-management-tools/bulk-troubleshooting.md).

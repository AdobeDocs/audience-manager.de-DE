---
description: Mit der Massenerstellung können Sie mehrere Datenquellen, abgeleitete Signale, Segmente, Eigenschaften und andere Elemente mit einem einzigen Vorgang erstellen. Befolgen Sie diese Anweisungen, um eine Massenerstellungsanforderung zu stellen.
seo-description: Bulk create lets you construct multiple data sources, derived signals, segments, traits, and other items with a single operation. Follow these instructions to make a bulk creation request.
seo-title: Bulk Create
solution: Audience Manager
title: Massenerstellung
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# Massenerstellung{#bulk-create}

Mit der Massenerstellung können Sie mehrere Datenquellen, abgeleitete Signale, Segmente, Eigenschaften und andere Elemente mit einem einzigen Vorgang erstellen. Befolgen Sie diese Anweisungen, um eine Massenerstellungsanforderung zu stellen.

>[!IMPORTANT]
>
>Die Tools für die Massenverwaltung sind kein offiziell unterstütztes Adobe-Angebot. Die Fehlerbehebung und der Support durch die Kundenunterstützung werden von Fall zu Fall durchgeführt.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[In der Benutzeroberfläche von [!DNL Audience Manager] zugewiesene RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) werden in der [!UICONTROL Bulk Management Tools] berücksichtigt.

>[!CAUTION]
>
>Mischen Sie keine Objekttypen in einer Massenerstellungsanforderung. Die Kopfzeilen für jedes Objekt sind eindeutig und können nicht kombiniert werden. Löschen Sie das Arbeitsblatt und stellen Sie eine separate Anfrage für verschiedene Elemente.

Um Objekte stapelweise zu erstellen, öffnen Sie das Arbeitsblatt [!UICONTROL Bulk Management Tools] und:

1. Klicken Sie auf die Registerkarte **[!UICONTROL Headers]** und kopieren Sie die Kopfzeilen zum Erstellen des Elements, das Sie hinzufügen möchten.
2. Klicken Sie auf die Registerkarte **[!UICONTROL Create]** .
3. Fügen Sie die Kopfzeilen zum Erstellen in die erste Zeile des Aktualisierungsarbeitsblatts ein.
4. Fügen Sie die Daten, die Sie ändern möchten, basierend auf der Kopfzeilenbeschriftung in eine entsprechende Spalte ein oder geben Sie sie ein.
5. Klicken Sie in der Symbolleiste des Arbeitsblatts auf die Schaltfläche Erstellen , die dem zu aktualisierenden Element entspricht.
Durch diese Aktion wird das Dialogfeld [!UICONTROL Account Information] geöffnet.
6. Geben Sie die erforderlichen [Anmeldedaten ](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) an und klicken Sie auf **[!UICONTROL Submit]**.

Das Arbeitsblatt erstellt eine [!UICONTROL Results] -Spalte. Die Spalte [!UICONTROL Results] gibt die JSON-Antwort für einen erfolgreichen Vorgang zurück. Beispiele finden Sie unter [REST APIs](../../api/rest-api-main/rest-api-main.md) . Vor der Eingabe von Daten sollte das Bulk-Arbeitsblatt zur Erstellung ähnlich wie im folgenden Beispiel aussehen. Beachten Sie, dass hier nicht alle verschiedenen Erstellungsoptionen angezeigt werden. Dieser Abschnitt enthält Informationen dazu, wie ein ausgefülltes Arbeitsblatt aussehen könnte.

![](assets/cretetraits.png)

Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Tools für die Massenverwaltung](../../reference/bulk-management-tools/bulk-troubleshooting.md).

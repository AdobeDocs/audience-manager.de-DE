---
description: Mit der Massenerstellung können Sie mehrere Datenquellen, abgeleitete Signale, Segmente, Eigenschaften und andere Elemente mit einem einzigen Vorgang erstellen. Befolgen Sie diese Anweisungen, um eine Massenerstellungsanforderung zu stellen.
seo-description: Mit der Massenerstellung können Sie mehrere Datenquellen, abgeleitete Signale, Segmente, Eigenschaften und andere Elemente mit einem einzigen Vorgang erstellen. Befolgen Sie diese Anweisungen, um eine Massenerstellungsanforderung zu stellen.
seo-title: Massenerstellungen
solution: Audience Manager
title: Massenerstellungen
uuid: 1e09bcfa-783e-4e9b-9ead-147f8d1381c8
feature: BAAAM
exl-id: 7828fc95-24eb-4a80-bdb8-0d9adea43d8f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# Massenerstellungen{#bulk-create}

Mit der Massenerstellung können Sie mehrere Datenquellen, abgeleitete Signale, Segmente, Eigenschaften und andere Elemente mit einem einzigen Vorgang erstellen. Befolgen Sie diese Anweisungen, um eine Massenerstellungsanforderung zu stellen.

<!-- 

t_bulk_create.xml

 -->

>[!NOTE]
>
>[In der ](../../features/administration/administration-overview.md) Benutzeroberfläche zugewiesene RBAC-Gruppenberechtigungen werden in der berücksichtigt  [!DNL Audience Manager]   [!UICONTROL Bulk Management Tools].

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
6. Geben Sie die erforderlichen [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) ein und klicken Sie auf **[!UICONTROL Submit]**.

Das Arbeitsblatt erstellt eine [!UICONTROL Results] -Spalte. Die Spalte [!UICONTROL Results] gibt die JSON-Antwort für einen erfolgreichen Vorgang zurück. Beispiele finden Sie unter [REST-APIs](../../api/rest-api-main/rest-api-main.md) . Vor der Eingabe von Daten sollte das Bulk-Arbeitsblatt zur Erstellung ähnlich wie im folgenden Beispiel aussehen. Beachten Sie, dass hier nicht alle verschiedenen Erstellungsoptionen angezeigt werden. Dieser Abschnitt enthält Informationen dazu, wie ein ausgefülltes Arbeitsblatt aussehen könnte.

![](assets/cretetraits.png)

Wenn Ihre Massenaktualisierung einen Fehler zurückgibt oder fehlschlägt, finden Sie weitere Informationen unter [Fehlerbehebung für Massenverwaltungswerkzeuge](../../reference/bulk-management-tools/bulk-troubleshooting.md).

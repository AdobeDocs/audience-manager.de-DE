---
description: Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften, Modelle, Datenquellen und Segment- oder Eigenschaftenordnerelemente in einem Vorgang bearbeiten. Befolgen Sie diese Anweisungen, um Massenaktualisierungen durchzuführen.
keywords: baaam
seo-description: A bulk update lets you edit multiple segments, traits, models, data sources, and segment or trait folder elements in a single operation. Follow these instructions to make bulk updates.
seo-title: Bulk Updates
solution: Audience Manager
title: Massenaktualisierungen
uuid: 22f1badd-a274-4d3e-9957-a24bf8c1d0dc
feature: BAAAM
exl-id: ef01c7d0-5af1-4db7-9859-1087c1fef684
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Massenaktualisierungen{#bulk-updates}

Mit einer Massenaktualisierung können Sie mehrere Segmente, Eigenschaften, Modelle, Datenquellen und Segment- oder Eigenschaftenordnerelemente in einem Vorgang bearbeiten. Befolgen Sie diese Anweisungen, um Massenaktualisierungen durchzuführen.

>[!IMPORTANT]
>
>Die Tools für die Massenverwaltung sind kein offiziell unterstütztes Adobe-Angebot. Die Fehlerbehebung und der Support durch die Kundenunterstützung werden von Fall zu Fall durchgeführt.

<!-- 

t_bulk_updates.xml

 -->

>[!NOTE]
>
>[RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) in der [!DNL Audience Manager] Die Benutzeroberfläche wird im Abschnitt [!UICONTROL Bulk Management Tools].

Um Massenaktualisierungen vorzunehmen, öffnen Sie die [!UICONTROL Bulk Management Tools] Arbeitsblatt und

1. Klicken Sie auf **[!UICONTROL Headers]** und kopieren Sie die Aktualisierungs-Header für das Element, das Sie bearbeiten möchten.
2. Klicken Sie auf **[!UICONTROL Update]** Registerkarte.
3. Fügen Sie die Aktualisierungskopfzeilen in die erste Zeile des Aktualisierungsarbeitsblatts ein. Beachten Sie Folgendes:

   * Beim Aktualisieren eines Ordners sind alle Header erforderlich.
   * Beim Aktualisieren von Segmenten oder Eigenschaften benötigen Sie nur die Segment-ID (SID) und das Kopfzeilenelement, das geändert werden muss. Nicht verwendete Kopfzeilen löschen

4. Fügen Sie die Daten, die Sie ändern möchten, basierend auf der Kopfzeilenbeschriftung in eine entsprechende Spalte ein oder geben Sie sie ein.
5. Klicken Sie in der Symbolleiste des Arbeitsblatts auf eine Aktualisierungsschaltfläche, die dem zu aktualisierenden Element entspricht.
Diese Aktion öffnet die [!UICONTROL Account Information] Dialogfeld.

6. Stellen Sie die erforderlichen [Informationen anmelden](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) und klicken **[!UICONTROL Submit]**.

   Das Arbeitsblatt erstellt eine [!UICONTROL Results] Spalte. Die [!UICONTROL Results] gibt die JSON-Antwort für einen erfolgreichen Vorgang zurück. Siehe [REST-APIs](../../api/rest-api-main/rest-api-main.md) für Beispiele. Vor der Eingabe von Daten sollte das Bulk Update-Arbeitsblatt in etwa wie folgt aussehen:

![](assets/update.png)

Wenn Ihre Massen-Aktualisierung einen Fehler zurückgibt oder fehlschlägt, lesen Sie [Fehlerbehebung für Tools zur Massenverwaltung](../../reference/bulk-management-tools/bulk-troubleshooting.md).

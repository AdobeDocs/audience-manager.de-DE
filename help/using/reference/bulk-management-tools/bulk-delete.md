---
description: Mit dem Massenlöschen können Sie mehrere Segmente, Eigenschaften, Ordner, abgeleitete Signale und Ziele mit einem einzelnen Vorgang entfernen. Befolgen Sie diese Anweisungen, um eine Massenlöschanforderung vorzunehmen.
seo-description: Mit dem Massenlöschen können Sie mehrere Segmente, Eigenschaften, Ordner, abgeleitete Signale und Ziele mit einem einzelnen Vorgang entfernen. Befolgen Sie diese Anweisungen, um eine Massenlöschanforderung vorzunehmen.
seo-title: Massenlöschung
solution: Audience Manager
title: Massenlöschung
uuid: 679 cde 46-09 fb -45 c 6-b 84 d -47 e 00 e 0 e 7 c 0 a
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Bulk Delete{#bulk-delete}

Mit dem Massenlöschen können Sie mehrere Segmente, Eigenschaften, Ordner, abgeleitete Signale und Ziele mit einem einzelnen Vorgang entfernen. Befolgen Sie diese Anweisungen, um eine Massenlöschanforderung vorzunehmen.

<!-- 

<p>t_bulk_delete.xml </p>

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

>[!NOTE]
>
>Eine Massenlöschung für Zielzuordnungen schlägt fehl, wenn Sie Segmente haben, die dem Ziel zugeordnet sind. Entfernen Sie Ihre Segmente aus diesem Ziel in der Benutzeroberfläche, bevor Sie Ziele löschen. Außerdem müssen Eigenschaften und Segmentordner leer sein, bevor sie sie löschen können.

To delete multiple items, open the [!UICONTROL Bulk Management Tools] worksheet and:

1. Click the **[!UICONTROL Headers]** tab and copy the create headers for the item you want to add.
2. Click the **[!UICONTROL Delete]** tab.
3. Fügen Sie die Löschkopfzeilen in die erste Zeile des Aktualisierungsarbeitsblatts ein.
4. Fügen Sie die IDs für die Objekte, die Sie löschen möchten, in der Spalte unterhalb der Kopfzeile ein oder aus.
5. Provide the required [log on information](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) and click **[!UICONTROL Submit]**.

   The worksheet creates a [!UICONTROL Results] column. The [!UICONTROL Results] column returns a message that indicates if the item has been deleted or an error message.
Vor der Eingabe der Daten sollte Ihr Massen-Updatesheet wie folgt aussehen:

![](assets/delete.png)

If your bulk update returns an error or fails, see [Troubleshooting for Bulk Management Tools](../../reference/bulk-management-tools/bulk-troubleshooting.md).

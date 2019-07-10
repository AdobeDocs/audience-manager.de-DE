---
description: Mit den Massenverwaltungswerkzeugen können Sie mehrere Objekte gleichzeitig mit einem einzelnen Vorgang erstellen und verwalten. Sie können Massenverwaltungswerkzeuge verwenden, um mit Datenquellen, abgeleiteten Signalen, Zielen, Ordnern, Segmenten und Eigenschaften zu arbeiten.
keywords: baaam; BAAAM
seo-description: Mit den Massenverwaltungswerkzeugen können Sie mehrere Objekte gleichzeitig mit einem einzelnen Vorgang erstellen und verwalten. Sie können Massenverwaltungswerkzeuge verwenden, um mit Datenquellen, abgeleiteten Signalen, Zielen, Ordnern, Segmenten und Eigenschaften zu arbeiten.
seo-title: Erste Schritte mit Massenverwaltung
solution: Audience Manager
title: Erste Schritte mit Massenverwaltung
uuid: 4 bc 6 ae 0 a -315 c -4 ce 7-a 68 e-cc 0 c 6 c 6 aa 2 f 1
translation-type: tm+mt
source-git-commit: f6fd1b99467a35b3f2c978c4b2e28d562eaa3c52

---


# Getting Started With Bulk Management{#getting-started-with-bulk-management}

Mit den Massenverwaltungswerkzeugen können Sie mehrere Objekte gleichzeitig mit einem einzelnen Vorgang erstellen und verwalten. Sie können Massenverwaltungswerkzeuge verwenden, um mit Datenquellen, abgeleiteten Signalen, Zielen, Ordnern, Segmenten und Eigenschaften zu arbeiten.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>The [!UICONTROL Bulk Management Tools] *are not* supported by [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. For bulk changes, we recommend that you work with the [Audience Manager APIs](../../api/rest-api-main/aam-api-getting-started.md) instead. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

## Überblick {#overview}

This feature uses a Microsoft Excel spreadsheet with macros that make secure, authenticated calls to the [!DNL Audience Manager] APIs. Die API stellt die Methoden und Dienste bereit, mit denen Sie Massenänderungen vornehmen können. Sie müssen nicht wissen, wie Sie mit unseren apis codieren oder mit diesen arbeiten können. Das Arbeitsblatt enthält Spaltenüberschriften und Registerkarten mit bestimmten Massenänderungsfunktionen. Um Massenänderungen vorzunehmen, fügen Sie nur die vordefinierten Header zu bestimmten Arbeitsblättern hinzu, geben die zu ändernden Informationen an und klicken auf eine Aktionsschaltfläche. Das Arbeitsblatt und die apis führen den Rest der Arbeit aus.

## Voraussetzungen {#prereqs}

To use the [!DNL Bulk Management Tools], you need the following:

* Your [!DNL Audience Manager] user name and password. Als Kunde sollten Sie bereits über diese Anmeldeinformationen verfügen.
* API-Client-ID und geheimer Schlüssel. Ihr Kundenbetreuer kann Ihnen diese bereitstellen.
* The [!UICONTROL Bulk Management Tools] worksheet. **[Laden Sie das Arbeitsblatt](assets/BAAAM_August_2018.xlsm)** herunter, um die neueste Version zu erhalten.

* Microsoft Excel running on [!DNL Windows] or in a [!DNL Microsoft Windows] virtual machine running on [!DNL macOS X]. You must use 32-bit Excel for the [!UICONTROL Bulk Management Tools] to work.

## Actions and operations {#actions-ops}

The [!UICONTROL Bulk Management Tools] worksheet consists of action tabs, action buttons, and a **[!UICONTROL Headers]** tab. The **[!UICONTROL Headers]** tab contains the pre-formatted column headers used by the action tabs. Die Registerkarten für Aktionen enthalten Makros, die Ihre ausgewählte Massenoperation durchführen. Um einen Massenvorgang durchzuführen, kopieren Sie einen Satz von Headern in die entsprechende Aktion, geben Kopfzeilendaten ein und klicken auf eine Aktionsschaltfläche.

Öffnen Sie das Arbeitsblatt und klicken Sie auf eine Aktionsschaltfläche, um zu beginnen.

![](assets/bamwrkbk.png)

The table below lists the operations you can perform and items you can manipulate with the [!UICONTROL Bulk Management Tools] worksheets.

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Aktionen </th> 
   <th colname="col2" class="entry"> Objekte </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Massenaktionen werden unten im Arbeitsblatt auf Registerkarten angezeigt und umfassen: </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Anforderungen </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Aktualisieren </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Erstellung     </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Schätzung </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Löschen </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>The objects you can change in bulk are located under the <b><span class="uicontrol"> Headers</span></b> tab and include: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Datenquellen</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Abgeleitete Signale</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> Ziele</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Eigenschaften</a> von Eigenschaften und Segmentordnern </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> Segmente</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> Eigenschaften</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispiel für einen Massenvorgang**

Als Beispiel sehen wir, wie Sie mehrere Eigenschaften gleichzeitig erstellen. So erstellen Sie mehrere Eigenschaften in einem Massenvorgang:

1. Click the **[!UICONTROL Headers]** tab and copy all the labels under the [!UICONTROL Create a Trait] option.

2. Click the **[!UICONTROL Create]** tab and paste the labels starting in row 1, column A.
3. Provide information related to each column header and click **[!UICONTROL Create Traits]**. Diese Aktion fordert Sie auf, sich anzumelden. Your bulk job runs after you successfully authenticate (see the [authentication requirements](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) below). Überprüfen Sie die untere linke Ecke des Arbeitsblatts für eine Benachrichtigung über einen Auftragsstatus.

>[!NOTE]
>
>Wenn Sie mit großen Anforderungen arbeiten, reagiert das Arbeitsblatt möglicherweise nicht mehr und kann nicht aktiv sein. Lassen Sie dies in diesen Fällen einfach allein. Das Arbeitsblatt wird reagiert, wenn die Massenanforderung abgeschlossen ist. If the worksheet does not respond for a long period of time, see the [troubleshooting section](../../reference/bulk-management-tools/bulk-troubleshooting.md).

## Authentication requirements and options {#auth-reqs}

Massenänderungen erfordern Authentifizierung. Wenn Sie eine Aktion auswählen, werden Sie aufgefordert, sich anzumelden. Da das Arbeitsblatt API-Aufrufe macht, müssen Sie es konfigurieren, um Ihren geheimen Schlüssel zu lesen. And, the **[!UICONTROL Domain]** field lets you make bulk changes in a staging/test environment or against your live, production account.

![](assets/bamauth.png)

**API-Authentifizierungsanforderungen**

Um die API-Authentifizierung einzurichten, müssen Sie Folgendes tun:

* Kopieren Sie den geheimen Schlüssel in einer Textdatei (.txt) und speichern Sie ihn.
* Benennen Sie die Textdatei mit Ihrer API-Client-ID. Wenn Ihre Client-ID beispielsweise &quot;Bulk-User&quot; lautet, speichern Sie den Schlüssel in einer Datei mit dem Titel&quot; Bulk-User. txt&quot; .
* Speichern Sie den geheimen Schlüssel und Arbeitsblatt im selben Ordner.

Wenn Sie Massenänderungen vornehmen, müssen Sie weiterhin einen Benutzernamen, ein Kennwort, eine Client-ID und eine Domäne eingeben, die API-Authentifizierung ist jedoch automatisch.

**Domänenauthentifizierungsoptionen**

Mit der Domänenauthentifizierung können Sie die Massenanforderungen testen oder sie direkt auf Ihr Produktionskonto anwenden. Massenänderungen an der Testumgebung wirken sich nicht auf Ihr Produktionskonto aus. Produktionsänderungen sind sofort wirksam. The **[!UICONTROL Domain]** field accepts the following addresses, depending on the environment you want to work in:

* Test läuft: `api-beta.demdex.com`
* Produktion: `api.demdex.com`

>[!MORE_ LIKE_ THIS]
>
>* [Herunterladen des Massenverwaltungsarbeitsblatts](assets/BAAAM_August_2018.xlsm)


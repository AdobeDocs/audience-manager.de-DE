---
description: Mit den Massenverwaltungswerkzeugen können Sie mehrere Objekte gleichzeitig mit einem einzigen Vorgang erstellen und verwalten. Mit den Massenverwaltungswerkzeugen können Sie mit Datenquellen, abgeleiteten Signalen, Zielen, Ordnern, Segmenten und Eigenschaften arbeiten.
keywords: baaam;BAAAM
seo-description: Mit den Massenverwaltungswerkzeugen können Sie mehrere Objekte gleichzeitig mit einem einzigen Vorgang erstellen und verwalten. Mit den Massenverwaltungswerkzeugen können Sie mit Datenquellen, abgeleiteten Signalen, Zielen, Ordnern, Segmenten und Eigenschaften arbeiten.
seo-title: Erste Schritte mit der Massenverwaltung
solution: Audience Manager
title: Erste Schritte mit der Massenverwaltung
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
translation-type: tm+mt
source-git-commit: 215054718e9248bd44ba99baeb2a10236701d98e

---


# Getting Started With Bulk Management{#getting-started-with-bulk-management}

Mit den Massenverwaltungswerkzeugen können Sie mehrere Objekte gleichzeitig mit einem einzigen Vorgang erstellen und verwalten. Mit den Massenverwaltungswerkzeugen können Sie mit Datenquellen, abgeleiteten Signalen, Zielen, Ordnern, Segmenten und Eigenschaften arbeiten.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>Die [!UICONTROL Bulk Management Tools] werden *nicht* von unterstützt [!DNL Audience Manager]. Dieses Tool wird nur aus praktischen Gründen und als Höflichkeit zur Verfügung gestellt. Bei Massenänderungen sollten Sie stattdessen mit den [Audience Manager-APIs](../../api/rest-api-main/aam-api-getting-started.md) arbeiten. [In der Benutzeroberfläche zugewiesene RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) werden berücksichtigt [!DNL Audience Manager] [!UICONTROL Bulk Management Tools].

## Überblick {#overview}

Diese Funktion verwendet eine Microsoft Excel-Tabelle mit Makros, die sichere, authentifizierte Aufrufe der [!DNL Audience Manager] APIs durchführen. Die API stellt die Methoden und Dienste bereit, mit denen Sie Massenänderungen vornehmen können. Sie müssen nicht wissen, wie Sie mit unseren APIs kodieren oder arbeiten, um sie zu verwenden. Das Arbeitsblatt enthält Spaltenüberschriften und Registerkarten, die bestimmte Massenänderungsfunktionen ausführen. Um Massenänderungen vorzunehmen, fügen Sie die vordefinierten Kopfzeilen nur bestimmten Arbeitsblättern hinzu, geben die Informationen an, die Sie stapelweise ändern möchten, und klicken Sie auf eine Aktionsschaltfläche. Das Arbeitsblatt und die APIs erledigen den Rest der Arbeit für Sie.

## Herunterladen{#download}.

Laden Sie das aktuelle Arbeitsblatt **[hier](assets/BAAAM_August_2018.xlsm)** herunter.

## Voraussetzungen {#prereqs}

Zur Verwendung der [!DNL Bulk Management Tools]Variablen benötigen Sie Folgendes:

* Ihr [!DNL Audience Manager] Benutzername und Ihr Kennwort. Als Kunde sollten Sie bereits über diese Anmeldeinformationen verfügen.
* Eine API-Client-ID und ein geheimer Schlüssel. Ihr Kundenbetreuer kann Ihnen diese bereitstellen.
* Das [!UICONTROL Bulk Management Tools] Arbeitsblatt. [Laden Sie das Arbeitsblatt](/help/using/reference/bulk-management-tools/bulk-management-intro.md#download) herunter, um die neueste Version zu erhalten.

* Microsoft Excel wird auf [!DNL Windows] oder auf einem [!DNL Microsoft Windows] virtuellen Computer ausgeführt, auf dem [!DNL macOS X]. Sie müssen Excel 32-Bit verwenden, damit die Anwendung funktioniert [!UICONTROL Bulk Management Tools] .

## Aktionen und Operationen {#actions-ops}

Das [!UICONTROL Bulk Management Tools] Arbeitsblatt besteht aus Registerkarten für Aktionen, Aktionsschaltflächen und einer **[!UICONTROL Headers]** Registerkarte. Die **[!UICONTROL Headers]** Registerkarte enthält die vorformatierten Spaltenüberschriften, die von den Registerkarten für Aktionen verwendet werden. Die Registerkarte "Aktion"enthält Makros, mit denen Sie den ausgewählten Massenvorgang durchführen. Um einen Massenvorgang auszuführen, kopieren Sie eine Reihe von Kopfzeilen in die entsprechende Registerkarte "Aktion", geben Kopfzeilendaten ein und klicken auf eine Aktionsschaltfläche.

Öffnen Sie die Tabelle und klicken Sie auf eine Aktionsschaltfläche, um zu beginnen.

![](assets/bamwrkbk.png)

Die folgende Tabelle listet die Vorgänge auf, die Sie durchführen können, und die Elemente, die Sie mit den [!UICONTROL Bulk Management Tools] Arbeitsblättern bearbeiten können.

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Aktionen </th> 
   <th colname="col2" class="entry"> Objekte </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Massenaktionen werden auf Registerkarten am unteren Ende des Arbeitsblatts angezeigt und umfassen: </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Anforderungen </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Aktualisieren </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Erstellung     </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Schätzung </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Löschen </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Die Objekte, die Sie stapelweise ändern können, befinden sich auf der Registerkarte " <b><span class="uicontrol"> Kopfzeilen</span></b> "und umfassen: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Datenquellen</a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Abgeleitete Signale</a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> Ziele</a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Eigenschaftenordner</a> und Segmentordner </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> Segmente</a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> Eigenschaften</a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Beispiel für Massenoperationen**

Sehen wir uns an, wie Sie mehrere Eigenschaften gleichzeitig erstellen. So erstellen Sie mehrere Eigenschaften in einem Massenvorgang:

1. Klicken Sie auf die **[!UICONTROL Headers]** Registerkarte und kopieren Sie alle Beschriftungen unter der [!UICONTROL Create a Trait] Option.

2. Klicken Sie auf die **[!UICONTROL Create]** Registerkarte und fügen Sie die Beschriftungen beginnend in Zeile 1 Spalte A ein.
3. Geben Sie Informationen zu den einzelnen Spaltenüberschriften an und klicken Sie auf **[!UICONTROL Create Traits]**. Diese Aktion fordert Sie auf, sich anzumelden. Ihr Massenauftrag wird nach erfolgreicher Authentifizierung ausgeführt (siehe [Authentifizierungsanforderungen](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) unten). Überprüfen Sie in der linken unteren Ecke des Arbeitsblatts, ob eine Benachrichtigung zum Auftragsstatus angezeigt wird.

>[!NOTE]
>
>Beim Arbeiten mit großen Anforderungen reagiert das Arbeitsblatt möglicherweise nicht mehr und scheint inaktiv zu sein. In diesen Fällen lassen Sie es einfach in Ruhe. Das Arbeitsblatt reagiert, wenn die Massenanforderung abgeschlossen ist. Wenn das Arbeitsblatt über einen langen Zeitraum nicht reagiert, finden Sie weitere Informationen im Abschnitt [Fehlerbehebung](../../reference/bulk-management-tools/bulk-troubleshooting.md).

## Authentifizierungsanforderungen und Optionen {#auth-reqs}

Massenänderungen erfordern eine Authentifizierung. Wenn Sie eine Aktion auswählen, werden Sie im Arbeitsblatt aufgefordert, sich anzumelden. Da das Arbeitsblatt API-Aufrufe ausführt, müssen Sie es so konfigurieren, dass der geheime Schlüssel gelesen wird. Außerdem können Sie im **[!UICONTROL Domain]** Feld Massenänderungen in einer Staging-/Testumgebung oder in Ihrem Live-Produktionskonto vornehmen.

![](assets/bamauth.png)

**API-Authentifizierungsanforderungen**

Zur Einrichtung der API-Authentifizierung müssen Sie:

* Kopieren Sie den geheimen Schlüssel und speichern Sie ihn in einer Textdatei (.txt).
* Benennen Sie die Textdatei mit Ihrer API-Client-ID. Wenn Ihre Client-ID beispielsweise "Massenbenutzer"lautet, speichern Sie den Schlüssel in der Datei "Bulk-User.txt".
* Speichern Sie den geheimen Schlüssel und das Arbeitsblatt gemeinsam im selben Ordner.

Bei Massenänderungen müssen Sie weiterhin einen Benutzernamen, ein Kennwort, eine Client-ID und eine Domäne eingeben. Die API-Authentifizierung erfolgt jedoch automatisch.

**Domänenauthentifizierungsoptionen**

Mit der Domänenauthentifizierung können Sie Massenanforderungen testen oder direkt auf Ihr Produktionskonto anwenden. Massenänderungen an der Testumgebung wirken sich nicht auf Ihr Produktionskonto aus. Produktionsänderungen sind sofort wirksam. Je nach Umgebung, in der Sie arbeiten möchten, akzeptiert das **[!UICONTROL Domain]** Feld die folgenden Adressen:

* Test läuft: `api-beta.demdex.com`
* Produktion: `api.demdex.com`

>[!MORE_LIKE_THIS]
>
>* [Massenverwaltungsarbeitsblatt herunterladen](assets/BAAAM_August_2018.xlsm)


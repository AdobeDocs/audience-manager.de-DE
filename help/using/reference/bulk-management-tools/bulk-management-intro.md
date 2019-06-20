---
description: Mit den Massenverwaltungswerkzeugen können Sie mehrere Objekte gleichzeitig mit einem einzelnen Vorgang erstellen und verwalten. Sie können Massenverwaltungswerkzeuge verwenden, um mit Datenquellen, abgeleiteten Signalen, Zielen, Ordnern, Segmenten und Eigenschaften zu arbeiten.
keywords: baaam; BAAAM
seo-description: Mit den Massenverwaltungswerkzeugen können Sie mehrere Objekte gleichzeitig mit einem einzelnen Vorgang erstellen und verwalten. Sie können Massenverwaltungswerkzeuge verwenden, um mit Datenquellen, abgeleiteten Signalen, Zielen, Ordnern, Segmenten und Eigenschaften zu arbeiten.
seo-title: Erste Schritte mit Massenverwaltung
solution: Audience Manager
title: Erste Schritte mit Massenverwaltung
uuid: 4 bc 6 ae 0 a -315 c -4 ce 7-a 68 e-cc 0 c 6 c 6 aa 2 f 1
translation-type: tm+mt
source-git-commit: 349cc962c993b361e2dea00ba693337391b87e5e

---


# Erste Schritte mit Massenverwaltung{#getting-started-with-bulk-management}

Mit den Massenverwaltungswerkzeugen können Sie mehrere Objekte gleichzeitig mit einem einzelnen Vorgang erstellen und verwalten. Sie können Massenverwaltungswerkzeuge verwenden, um mit Datenquellen, abgeleiteten Signalen, Zielen, Ordnern, Segmenten und Eigenschaften zu arbeiten.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>Die Variable [!UICONTROL Bulk Management Tools]*wird nicht* unterstützt [!DNL Audience Manager]. Dieses Tool wird zur Bequemlichkeit und nur als Freundlichkeit bereitgestellt. Für Massenänderungen wird empfohlen, stattdessen mit den [Audience Manager-apis](../../api/rest-api-main/aam-api-getting-started.md) zu arbeiten. [RBAC-Gruppenberechtigungen,](../../features/administration/administration-overview.md) die in der [!DNL Audience Manager] Benutzeroberfläche zugewiesen [!UICONTROL Bulk Management Tools]wurden, werden in der Benutzeroberfläche berücksichtigt.

## Überblick {#overview}

Diese Funktion verwendet eine Microsoft Excel-Tabelle mit Makros, die sichere, authentifizierte Aufrufe an [!DNL Audience Manager] die apis vornehmen. Die API stellt die Methoden und Dienste bereit, mit denen Sie Massenänderungen vornehmen können. Sie müssen nicht wissen, wie Sie mit unseren apis codieren oder mit diesen arbeiten können. Das Arbeitsblatt enthält Spaltenüberschriften und Registerkarten mit bestimmten Massenänderungsfunktionen. Um Massenänderungen vorzunehmen, fügen Sie nur die vordefinierten Header zu bestimmten Arbeitsblättern hinzu, geben die zu ändernden Informationen an und klicken auf eine Aktionsschaltfläche. Das Arbeitsblatt und die apis führen den Rest der Arbeit aus.

## Voraussetzungen {#prereqs}

Zur Verwendung [!DNL Bulk Management Tools]benötigen Sie Folgendes:

* Ihr [!DNL Audience Manager] Benutzername und Ihr Kennwort. Als Kunde sollten Sie bereits über diese Anmeldeinformationen verfügen.
* API-Client-ID und geheimer Schlüssel. Ihr Kundenbetreuer kann Ihnen diese bereitstellen.
* Das [!UICONTROL Bulk Management Tools] Arbeitsblatt. **[Laden Sie das Arbeitsblatt](assets/BAAAM_August_2018.xlsm)** herunter, um die neueste Version zu erhalten.

* Microsoft Excel auf [!DNL Windows] oder auf einem [!DNL Microsoft Windows] virtuellen Computer ausgeführt, auf [!DNL macOS X]dem ausgeführt wird. Sie müssen mit 32-Bit Excel [!UICONTROL Bulk Management Tools] arbeiten.

## Aktionen und Vorgänge {#actions-ops}

Das [!UICONTROL Bulk Management Tools] Arbeitsblatt besteht aus Aktionsregistern, Aktionsschaltflächen und einer **[!UICONTROL Headers]** Registerkarte. Die **[!UICONTROL Headers]** Registerkarte enthält die vorformatierten Spaltenüberschriften, die von den Aktionsregistern verwendet werden. Die Registerkarten für Aktionen enthalten Makros, die Ihre ausgewählte Massenoperation durchführen. Um einen Massenvorgang durchzuführen, kopieren Sie einen Satz von Headern in die entsprechende Aktion, geben Kopfzeilendaten ein und klicken auf eine Aktionsschaltfläche.

Öffnen Sie das Arbeitsblatt und klicken Sie auf eine Aktionsschaltfläche, um zu beginnen.

![](assets/bamwrkbk.png)

In der folgenden Tabelle sind die Vorgänge aufgelistet, die Sie ausführen können, sowie Elemente, die Sie mit den [!UICONTROL Bulk Management Tools] Arbeitsblättern bearbeiten können.

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
   <td colname="col2"> <p>Die Objekte, die Sie massenweise ändern können, befinden sich auf der Registerkarte <b><span class="uicontrol"> "Kopfzeile"</span></b> und umfassen Folgendes: </p> <p> 
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

1. Klicken Sie auf die **[!UICONTROL Headers]** Registerkarte und kopieren Sie alle Beschriftungen unter der [!UICONTROL Create a Trait] Option.

2. Klicken Sie auf die **[!UICONTROL Create]** Registerkarte und fügen Sie die Beschriftungen ab Zeile 1 in Spalte A ein.
3. Geben Sie Informationen zu den einzelnen Spaltenüberschriften an und klicken **[!UICONTROL Create Traits]** Sie auf. Diese Aktion fordert Sie auf, sich anzumelden. Ihr Massenauftrag wird nach erfolgreicher Authentifizierung ausgeführt (siehe [Authentifizierungsanforderungen](../../reference/bulk-management-tools/bulk-management-intro.md#auth-reqs) unten). Überprüfen Sie die untere linke Ecke des Arbeitsblatts für eine Benachrichtigung über einen Auftragsstatus.

>[!NOTE]
>
>Wenn Sie mit großen Anforderungen arbeiten, reagiert das Arbeitsblatt möglicherweise nicht mehr und kann nicht aktiv sein. Lassen Sie dies in diesen Fällen einfach allein. Das Arbeitsblatt wird reagiert, wenn die Massenanforderung abgeschlossen ist. Wenn das Arbeitsblatt auf lange Zeit nicht reagiert, lesen Sie den Abschnitt [zur Fehlerbehebung](../../reference/bulk-management-tools/bulk-troubleshooting.md).

## Authentifizierungsanforderungen und Optionen {#auth-reqs}

Massenänderungen erfordern Authentifizierung. Wenn Sie eine Aktion auswählen, werden Sie aufgefordert, sich anzumelden. Da das Arbeitsblatt API-Aufrufe macht, müssen Sie es konfigurieren, um Ihren geheimen Schlüssel zu lesen. Außerdem können Sie mit dem **[!UICONTROL Domain]** Feld Massenänderungen in einer Staging-/Testumgebung oder auf Ihrem Live-Produktionskonto vornehmen.

![](assets/bamauth.png)

**API-Authentifizierungsanforderungen**

Um die API-Authentifizierung einzurichten, müssen Sie Folgendes tun:

* Kopieren Sie den geheimen Schlüssel in einer Textdatei (.txt) und speichern Sie ihn.
* Benennen Sie die Textdatei mit Ihrer API-Client-ID. Wenn Ihre Client-ID beispielsweise &quot;Bulk-User&quot; lautet, speichern Sie den Schlüssel in einer Datei mit dem Titel&quot; Bulk-User. txt&quot; .
* Speichern Sie den geheimen Schlüssel und Arbeitsblatt im selben Ordner.

Wenn Sie Massenänderungen vornehmen, müssen Sie weiterhin einen Benutzernamen, ein Kennwort, eine Client-ID und eine Domäne eingeben, die API-Authentifizierung ist jedoch automatisch.

**Domänenauthentifizierungsoptionen**

Mit der Domänenauthentifizierung können Sie die Massenanforderungen testen oder sie direkt auf Ihr Produktionskonto anwenden. Massenänderungen an der Testumgebung wirken sich nicht auf Ihr Produktionskonto aus. Produktionsänderungen sind sofort wirksam. Je nach Umgebung, in der Sie arbeiten möchten, akzeptiert das **[!UICONTROL Domain]** Feld die folgenden Adressen:

* Test läuft: `api-beta.demdex.com`
* Produktion: `api.demdex.com`

>[!MORE_ LIKE_ THIS]
>
>* [Herunterladen des Massenverwaltungsarbeitsblatts](assets/BAAAM_August_2018.xlsm)


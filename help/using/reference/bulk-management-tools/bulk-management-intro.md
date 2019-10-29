---
description: Mit den Massenverwaltungswerkzeugen können Sie mehrere Objekte gleichzeitig mit einem einzigen Vorgang erstellen und verwalten. Mit den Massenverwaltungswerkzeugen können Sie mit Datenquellen, abgeleiteten Signalen, Zielen, Ordnern, Segmenten und Eigenschaften arbeiten.
keywords: baaam;BAAAM
seo-description: Mit den Massenverwaltungswerkzeugen können Sie mehrere Objekte gleichzeitig mit einem einzigen Vorgang erstellen und verwalten. Mit den Massenverwaltungswerkzeugen können Sie mit Datenquellen, abgeleiteten Signalen, Zielen, Ordnern, Segmenten und Eigenschaften arbeiten.
seo-title: Erste Schritte mit der Massenverwaltung
solution: Audience Manager
title: Erste Schritte mit der Massenverwaltung
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
translation-type: tm+mt
source-git-commit: be988def0e9cb5cb6b4a926754dd24f9fd1f85fe

---


# Getting Started With Bulk Management{#getting-started-with-bulk-management}

Mit den Massenverwaltungswerkzeugen können Sie mehrere Objekte gleichzeitig mit einem einzigen Vorgang erstellen und verwalten. Mit den Massenverwaltungswerkzeugen können Sie mit Datenquellen, abgeleiteten Signalen, Zielen, Ordnern, Modellen, Segmenten und Eigenschaften arbeiten.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>Die [!UICONTROL Bulk Management Tools] werden *nicht* von unterstützt [!DNL Audience Manager]. Dieses Tool wird nur aus praktischen Gründen und als Höflichkeit zur Verfügung gestellt. Bei Massenänderungen sollten Sie stattdessen mit den [Audience Manager-APIs](../../api/rest-api-main/aam-api-getting-started.md) arbeiten. [In der Benutzeroberfläche zugewiesene RBAC-Gruppenberechtigungen](../../features/administration/administration-overview.md) werden berücksichtigt [!DNL Audience Manager] [!UICONTROL Bulk Management Tools].

## Überblick {#overview}

Diese Funktion verwendet eine Microsoft Excel-Tabelle mit Makros, die sichere, authentifizierte Aufrufe der [!DNL Audience Manager] APIs durchführen. Die API stellt die Methoden und Dienste bereit, mit denen Sie Massenänderungen vornehmen können. Sie müssen nicht wissen, wie Sie mit unseren APIs kodieren oder arbeiten, um sie zu verwenden. Das Arbeitsblatt enthält Spaltenüberschriften und Registerkarten, die bestimmte Massenänderungsfunktionen ausführen. Um Massenänderungen vorzunehmen, fügen Sie die vordefinierten Kopfzeilen nur bestimmten Arbeitsblättern hinzu, geben die Informationen an, die Sie stapelweise ändern möchten, und klicken Sie auf eine Aktionsschaltfläche. Das Arbeitsblatt und die APIs erledigen den Rest der Arbeit für Sie.

## Herunterladen{#download}.

Laden Sie das aktuelle Arbeitsblatt **[hier](assets/BAAAM_V2_20191015.xlsm)** herunter.

## Voraussetzungen {#prereqs}

Zur Verwendung der [!DNL Bulk Management Tools]Variablen benötigen Sie Folgendes:

* Ihre [!DNL Experience Cloud] Anmeldung. Als Kunde sollten Sie bereits über diese Anmeldeinformationen verfügen.
* Das [!DNL Bulk Management Tools] Arbeitsblatt. [Laden Sie das Arbeitsblatt](/help/using/reference/bulk-management-tools/bulk-management-intro.md#download) herunter, um die neueste Version zu erhalten.
* Microsoft Excel wird auf [!DNL macOS] oder 64 Bit ausgeführt [!DNL Microsoft Windows].
* Beim Öffnen des Arbeitsblatts müssen Sie Makros **** aktivieren, damit das Arbeitsblatt funktioniert [!DNL Bulk Management Tools] .

## Authentifizierungsanforderungen und Optionen {#auth-reqs}

Massenänderungen erfordern eine Authentifizierung. Bevor Sie eine Aktion durchführen, müssen Sie sich anmelden. Da das Arbeitsblatt API-Aufrufe ausführt, müssen Sie es für die Authentifizierung in Ihrem Benutzerkonto konfigurieren.

**API-Authentifizierungsanforderungen**

Die im Oktober 2019 veröffentlichte zweite Version der Bulk Management Tools vereinfacht den Authentifizierungsprozess. Die Authentifizierungsschritte in dieser Version sind nachfolgend beschrieben:

1. Öffnen Sie die Tabelle und navigieren Sie zum **Konfigurationsblatt** .
2. Führen Sie die im Arbeitsblatt beschriebenen Schritte aus.
   ![](assets/baaam-authentication.png)
3. Nach Abschluss der Schritte sind Sie berechtigt, Massenänderungen vorzunehmen.

Beim Durchführen von Massenänderungen müssen Sie weiterhin bestätigen, dass Sie berechtigt sind, die Änderungen vorzunehmen. Die API-Authentifizierung ist jedoch automatisch.

**Domänenauthentifizierungsoptionen**

Mit der Domänenauthentifizierung können Sie Massenanforderungen testen oder direkt auf Ihr Produktionskonto anwenden. Massenänderungen an der Betaumgebung haben keine Auswirkungen auf Ihr Produktionskonto. Produktionsänderungen sind sofort wirksam. Das Bulk Management Sheet ermöglicht Ihnen, in den folgenden Umgebungen zu arbeiten:

* Beta
* Produktion

## Aktionen und Operationen {#actions-ops}

Das [!UICONTROL Bulk Management Tools] Arbeitsblatt besteht aus Authentifizierungsschaltflächen, Aktionsregisterkarten, Aktionsschaltflächen und einer **[!UICONTROL Headers]** Registerkarte. Die **[!UICONTROL Headers]** Registerkarte enthält die vorformatierten Spaltenüberschriften, die von den Registerkarten für Aktionen verwendet werden. Die Registerkarte "Aktion"enthält Makros, mit denen Sie den ausgewählten Massenvorgang durchführen. Um einen Massenvorgang auszuführen, kopieren Sie eine Reihe von Kopfzeilen in die entsprechende Registerkarte "Aktion", geben Kopfzeilendaten ein und klicken auf eine Aktionsschaltfläche.

Klicken Sie nach der [Authentifizierung](#auth-reqs)auf eine Aktionsschaltfläche, um zu beginnen.

![](assets/baaam-worksheet.png)

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
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> Modelle</a> </li> 
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
3. Geben Sie Informationen zu den einzelnen Spaltenüberschriften an und klicken Sie auf **[!UICONTROL Create Traits]**. Diese Aktion fordert Sie zur Bestätigung Ihrer Authentifizierung auf. Ihr Massenauftrag wird ausgeführt, nachdem Sie Ihre Authentifizierung bestätigt haben. Überprüfen Sie in der linken unteren Ecke des Arbeitsblatts, ob eine Benachrichtigung zum Auftragsstatus angezeigt wird.


>[!NOTE]
>
>Beim Arbeiten mit großen Anforderungen reagiert das Arbeitsblatt möglicherweise nicht mehr und scheint inaktiv zu sein. In diesen Fällen lassen Sie es einfach in Ruhe. Das Arbeitsblatt reagiert, wenn die Massenanforderung abgeschlossen ist. Wenn das Arbeitsblatt über einen langen Zeitraum nicht reagiert, finden Sie weitere Informationen im Abschnitt [Fehlerbehebung](../../reference/bulk-management-tools/bulk-troubleshooting.md).



>[!MORE_LIKE_THIS]
>
>* [Massenverwaltungsarbeitsblatt herunterladen](assets/BAAAM_August_2018.xlsm)


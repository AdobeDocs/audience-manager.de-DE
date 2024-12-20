---
description: Ein privater Daten-Feed ist eine Option, mit der Anbieter den Käuferzugriff auf ihre Daten einschränken können. Datenanbieter und -käufer sollten diese Informationen überprüfen, bevor sie private Daten-Feeds erstellen und abonnieren.
seo-description: A private data feed is an option that lets providers limit buyer access to their data. Data providers and buyers should review this information before creating and subscribing to private data feeds.
seo-title: Private Data Feeds
solution: Audience Manager
title: private Datenfeeds
uuid: e4ca59ca-bbc9-4897-9374-8f3d54b2beee
feature: Audience Marketplace
exl-id: 34eb6194-c57b-4836-a6df-6889a2cec703
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 1%

---

# private Datenfeeds {#private-data-feeds}

Ein privater Daten-Feed ist eine Option, mit der Anbieter den Käuferzugriff auf ihre Daten einschränken können. Datenanbieter und -käufer sollten diese Informationen überprüfen, bevor sie private Daten-Feeds erstellen und abonnieren.

<!-- c_marketplace_privatefeed.xml -->

## Private Daten-Feeds für Anbieter {#private-data-feeds-providers}

Als Anbieter können Ihre Daten-Feeds öffentlich oder privat sein. Mit einem privaten Daten-Feed können Sie den Käuferzugriff auf Ihre Daten, einschließlich des Namens des Datenverkäufers, einschränken. Sie können einen privaten Daten-Feed erstellen, um Sonderangebote, Rabatte oder Informationen anzubieten, wenn Datenschutz und Zugriffskontrolle wichtig sind. Mit einem privaten Daten-Feed können Sie Käuferanfragen überprüfen und genehmigen. Nachdem Sie eine Anfrage genehmigt haben, sieht der Feed für den Käufer wie ein öffentlicher Daten-Feed aus. Sie können alle Ihre Feeds in **[!UICONTROL Audience Marketplace > My Shared Data]** anzeigen und verwalten. Wie unten gezeigt, ist dieser Feed-Typ in der Statusspalte mit „Privat“ gekennzeichnet.

![](assets/my_shared_data.png)

### Verwalten von Feed-Anfragen

Wenn Sie in [!UICONTROL My Shared Data] auf den Namen eines privaten Daten-Feeds klicken, gelangen Sie zu einer Seite mit mehreren Registerkarten. Klicken Sie auf eine Registerkarte, um Ihre privaten Daten-Feed-Anfragen zu verwalten.

![](assets/shared_data_tabs.png)

In der folgenden Tabelle werden die Rollen definiert, die von den einzelnen Aktionsregisterkarten bereitgestellt werden.

<table id="table_AFB429CA52A34658859448D9A5215F9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tab </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> aktuelle Abonnenten</span></b> </p> </td> 
   <td colname="col2"> <p>Listet zugelassene Käufer auf, die einen privaten Daten-Feed abonniert haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> potenzielle Abonnenten</span></b> </p> </td> 
   <td colname="col2"> <p>Listet zugelassene Käufer auf, die keinen privaten Daten-Feed abonniert haben. </p> <p>Mit einer Genehmigung können Käuferinnen und Käufer einen Daten-Feed so anzeigen, als wäre er öffentlich. Dies gibt ihnen die Möglichkeit, Ihre Feeds zu überprüfen und zu bewerten, bevor sie sich anmelden. Sie können Käufern, die als potenzielle Abonnenten aufgeführt sind, auch Rabatte auf Daten-Feeds anbieten. Sobald der Käufer sich angemeldet hat, wechselt sein Profil zu <b><span class="uicontrol"> aktuellen Abonnenten</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Zugriffsanfragen</span></b> </p> </td>
   <td colname="col2"> <p>Listet neue Abonnementanfragen für einen privaten Daten-Feed auf. Klicken Sie auf diese Registerkarte, um Käuferanfragen zu prüfen, zu genehmigen oder abzulehnen. </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">Zugelassene Käufer wechseln zu <b><span class="uicontrol"> potenziellen Abonnenten</span></b>. </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">Abgelehnte Käufer ziehen in <b><span class="uicontrol"> Zugriff verweigert</span></b>. </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Anfragen</span></b> </p> </td>
   <td colname="col2"> <p>Listet zugelassene Käufer auf, die noch keinen Daten-Feed abonniert haben und weitere Informationen zu Ihren Feeds angefordert haben. </p> <p>Mit einer Genehmigung können Käuferinnen und Käufer einen Daten-Feed so anzeigen, als wäre er öffentlich. Dies gibt ihnen die Möglichkeit, Ihre Feeds zu überprüfen und zu bewerten, bevor sie sich anmelden. Sie können Käufern, die Zugriff anfordern, auch Rabatte auf Daten-Feeds anbieten. Wenn Sie auf eine Detailanfrage antworten, wird das Käuferprofil aus dieser Registerkarte entfernt. Wenn er sich nicht angemeldet hat, befindet sich das Käuferprofil noch in <b><span class="uicontrol"> potenziellen Abonnenten</span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Zugriff verweigert</span></b> </p> </td> 
   <td colname="col2"> <p>Listet abgelehnte Abonnementanfragen für einen privaten Daten-Feed auf. </p> <p>Um abgelehnte Käufer erneut zu genehmigen, ändern Sie den <span class="wintitle"> Ablehnungsstatus </span> <b><span class="uicontrol"> „Zulassen</span></b>. Dadurch wird der Käufer zu <b><span class="uicontrol"> potenziellen Abonnenten </span></b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Nächste Schritte

Die folgende Dokumentation kann Ihnen bei den ersten Schritten mit privaten Daten-Feeds helfen.

* [Erstellen eines öffentlichen oder privaten Daten-Feeds](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [Private Feed-Anfragen überprüfen, genehmigen oder ablehnen](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [Private Daten-Feeds für Käufer](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## Private Daten-Feeds für Käufer {#private-data-feeds-for-buyers}

Als Käufer erscheinen private Daten-Feeds im [Marketplace](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace) wie jedes andere Angebot. In diesem Fall zeigt die Feed-Liste jedoch keine zusammenfassenden Informationen zu Eigenschaften, eindeutigen Benutzern und Benutzerüberschneidungen an. Außerdem hat der Datenverkäufer die Möglichkeit, seinen Namen in der [!UICONTROL Provider] Spalte der [!UICONTROL Marketplace] ein- oder auszublenden. Nachdem der Verkäufer Ihre Abonnementanfrage genehmigt hat, stehen Ihnen alle Daten in einem privaten Feed zur Verfügung (es funktioniert wie ein öffentlicher Feed). Das [!UICONTROL Marketplace] Beispiel unten listet die 3 verschiedenen Feed-Typen auf, die Ihnen als Käufer zur Verfügung stehen.

![](assets/buyer_marketplace.png)

Zu den Feed-Typen gehören:

Die folgende Tabelle beschreibt, wie diese verschiedenen Feed-Typen Daten anzeigen oder ausblenden.

<table id="table_41D4A798ACF548A3A03ACB427CA4652D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feed-Typ </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> öffentlich</span></b> </p> </td> 
   <td colname="col2"> <p>Der Name, die Eigenschaft und die eindeutigen Daten des Anbieters werden in der Liste angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> privat ohne Branding</span></b> </p> </td> 
   <td colname="col2"> <p>Der Name des Anbieters ist auf „Privater Verkäufer“ festgelegt, und Sie können keine Eigenschaftszählungen, eindeutigen Daten und Eigenschaftsüberschneidungsdaten sehen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> privat mit Branding</span></b> </p> </td> 
   <td colname="col2"> <p>Der Name des Anbieters wird in der Liste angezeigt, Sie können jedoch keine Eigenschaftszählungen, eindeutigen Daten und Eigenschaftsüberschneidungsdaten sehen. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Nächste Schritte

Siehe [Abonnieren eines privaten Daten-Feeds](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) um Zugriff anzufordern.

## Einrichten der Freigabebeziehung zwischen dem Datenanbieter und dem Datenkäufer {#set-up-sharing-relationship}

### Schritt 1: Aktivierung - Datenanbieter und Datenkäufer

Der erste Schritt im Prozess erfordert das Eingreifen von Adobe Consulting oder der Kundenunterstützung. Datenanbieter und Datenkäufer sollten sich an Adobe Consulting oder die Kundenunterstützung wenden, um die Aktivierung anzufordern.

### Schritt 2: Datenanbieter - Neue Daten in Source erstellen

Erstellen Sie in Ihrem Audience Manager-Konto eine neue Cookie-Datenquelle mit:

* **Audience Manager-ID** als Eingangsschlüssel;
* Die Option **Freigabe aktiviert** ist aktiviert.

![](assets/create-datasource.png)

Wenn Sie auf **Speichern** klicken, wird automatisch ein neuer Unterordner unter **Eigenschaftenspeicher > Drittanbieterdaten** erstellt.

![](assets/folder-structure.png)

### Schritt 3: Datenanbieter - Identifizieren von Eigenschaften für die Freigabe

In diesem Schritt identifizieren Sie die Eigenschaften, die Sie mit Ihrem Partner teilen möchten. Sie können entweder neue Eigenschaften erstellen oder vorhandene Eigenschaften bearbeiten. In jedem Fall benötigen Sie die Eigenschaften:

* Mit der Datenquelle zu verknüpfen, die Sie in Schritt 2 erstellt haben.
* Wird im neu erstellten Unterordner unter den Drittanbieterdaten gespeichert.

Lesen Sie mehr über [Erstellen von Eigenschaften](/help/using/features/traits/create-onboarded-rule-based-traits.md) und [Bearbeiten von Eigenschaften](/help/using/features/traits/manage-trait-rules.md#edit-trait).

### Schritt 4: Datenanbieter - Daten-Feed erstellen

Erstellen Sie als Nächstes einen Daten-Feed, um Ihre Eigenschaften mit dem Datenkäufer zu teilen. Anweisungen [ Erstellen eines öffentlichen oder privaten Daten-Feeds finden ](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md) unter „Erstellen eines öffentlichen oder privaten Daten-Feeds“.

>[!IMPORTANT]
>
>Wählen Sie unter Einstellungen die Option Privat aus. Wenn Sie dieses Feld auf Öffentlich setzen, kann jeder Audience Marketplace-Kunde Ihren Feed abonnieren.

![](assets/create-data-feed.png)

### Schritt 5: Datenerwerber - Zugriff anfordern

Gehen Sie zu **Audience Marketplace > Marketplace**. Suchen Sie nach dem vom Datenanbieter im vorherigen Schritt erstellten Daten-Feed. Klicken Sie **Zugriff anfordern**. Der von der Datenanbieterseite benannte Kontakt erhält nun eine E-Mail-Benachrichtigung. Siehe auch [Abonnieren eines privaten Daten-Feeds](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

### Schritt 6: Datenanbieter - Zugriff gewähren

Gehen Sie zu **Audience Marketplace > Meine freigegebenen Daten** und suchen Sie nach dem Feed, den Sie in Schritt 4 erstellt haben. Klicken Sie auf die neue Zugriffsanfrage und dann auf **Zugriff zulassen**, um die Anfrage zu genehmigen. Siehe auch [Prüfen, Genehmigen oder Ablehnen privater Feed-Anfragen](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests).

### Schritt 7: Datenerwerber - Abonnement aktivieren

Nachdem der Datenanbieter Zugriff auf den Daten-Feed gewährt hat, können Sie den Feed in Ihrem Konto unter **Audience Marketplace > Marketplace** sehen. Überprüfen Sie die Details, aktivieren Sie die Schaltfläche Abonnement und klicken Sie auf **Überprüfen und abonnieren**. Unter [Speicherung für abonnierte Daten-Feeds](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee) finden Sie Informationen darüber, wo die Drittanbieter-Eigenschaften zu finden sind.

Beachten Sie, dass diese Eigenschaften nur im Konto des Datenanbieters bearbeitet werden können.

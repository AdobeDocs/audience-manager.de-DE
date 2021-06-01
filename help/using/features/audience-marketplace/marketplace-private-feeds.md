---
description: Ein privater Daten-Feed ist eine Option, mit der Anbieter den Käuferzugriff auf ihre Daten einschränken können. Datenanbieter und -käufer sollten diese Informationen lesen, bevor sie private Daten-Feeds erstellen und abonnieren.
seo-description: Ein privater Daten-Feed ist eine Option, mit der Anbieter den Käuferzugriff auf ihre Daten einschränken können. Datenanbieter und -käufer sollten diese Informationen lesen, bevor sie private Daten-Feeds erstellen und abonnieren.
seo-title: Private Daten-Feeds
solution: Audience Manager
title: Private Daten-Feeds
uuid: e4ca59ca-bbc9-4897-9374-8f3d54b2beee
feature: Audience Marketplace
exl-id: 34eb6194-c57b-4836-a6df-6889a2cec703
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---

# Private Daten-Feeds {#private-data-feeds}

Ein privater Daten-Feed ist eine Option, mit der Anbieter den Käuferzugriff auf ihre Daten einschränken können. Datenanbieter und -käufer sollten diese Informationen lesen, bevor sie private Daten-Feeds erstellen und abonnieren.

<!-- c_marketplace_privatefeed.xml -->

## Private Daten-Feeds für Anbieter {#private-data-feeds-providers}

Als Anbieter können Ihre Daten-Feeds öffentlich oder privat sein. Mit einem privaten Daten-Feed können Sie den Käuferzugriff auf Ihre Daten einschränken, einschließlich des Namens des Datenverkäufers. Sie können einen privaten Daten-Feed erstellen, um spezielle Angebote, Rabatte oder wichtige Datenschutz- und Zugriffskontrollen anzubieten. Mit einem privaten Daten-Feed können Sie Kaufanfragen überprüfen und genehmigen. Nachdem Sie eine Anforderung genehmigt haben, sieht der Feed wie ein öffentlicher Daten-Feed für den Käufer aus. Sie können alle Ihre Feeds in **[!UICONTROL Audience Marketplace > My Shared Data]** anzeigen und verwalten. Wie unten gezeigt, wird dieser Feed-Typ in der Statusspalte mit &quot;Privat&quot;markiert.

![](assets/my_shared_data.png)

### Verwalten von Feed-Anforderungen

Durch Klicken auf den Namen eines privaten Daten-Feeds von [!UICONTROL My Shared Data] gelangen Sie zu einer Seite, die mehrere Registerkarten enthält. Klicken Sie auf eine Registerkarte, um Ihre privaten Daten-Feed-Anforderungen zu verwalten.

![](assets/shared_data_tabs.png)

In der folgenden Tabelle sind die Rollen bzw. Funktionen definiert, die von den einzelnen Aktionsregistern bereitgestellt werden.

<table id="table_AFB429CA52A34658859448D9A5215F9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tab </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Aktuelle Abonnenten</span></b> </p> </td> 
   <td colname="col2"> <p>Listet genehmigte Käufer auf, die einen privaten Daten-Feed abonniert haben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Potenzielle Abonnenten</span></b> </p> </td> 
   <td colname="col2"> <p>Listet genehmigte Käufer auf, die keinen privaten Daten-Feed abonniert haben. </p> <p>Mit einer Genehmigung können Käufer einen Daten-Feed so anzeigen, als wäre er öffentlich. Dadurch erhalten sie die Möglichkeit, Ihre Feeds vor dem Abonnieren zu überprüfen und zu bewerten. Darüber hinaus können Sie Käufern, die als potenzielle Abonnenten aufgeführt sind, Rabatte auf Daten-Feeds anbieten. Sobald sich der Käufer angemeldet hat, wechselt sein Profil zu <b><span class="uicontrol"> Aktuelle Abonnenten</span></b>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Zugriffsanforderungen</span></b> </p> </td>
   <td colname="col2"> <p>Listet neue Abonnementanforderungen für einen privaten Daten-Feed auf. Klicken Sie auf diesen Tab, um Käuferanfragen zu überprüfen, zu genehmigen oder abzulehnen. </p>
    <ul id="ul_BE0A835A90B14C05B3F63226B79D052D"> 
     <li id="li_2C5686CEB6F4430BA18AED5AD75C330A">Genehmigte Käufer wechseln zu <b><span class="uicontrol"> Potenzielle Abonnenten</span></b>. </li>
     <li id="li_929591FCF81E43A3881813BDBD3AC278">Abgelehnte Käufer wechseln zu <b><span class="uicontrol"> Verweisender Zugriff</span></b>. </li>
    </ul> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Detailanforderungen</span></b> </p> </td>
   <td colname="col2"> <p>Listet genehmigte Käufer auf, die sich noch nicht für einen Daten-Feed angemeldet haben und weitere Informationen zu Ihren Feeds angefordert haben. </p> <p>Mit einer Genehmigung können Käufer einen Daten-Feed so anzeigen, als wäre er öffentlich. Dadurch erhalten sie die Möglichkeit, Ihre Feeds vor dem Abonnieren zu überprüfen und zu bewerten. Darüber hinaus können Sie Käufern, die Zugriff anfordern, Rabatte auf Daten-Feeds anbieten. Wenn Sie auf eine Detailanfrage antworten, wird das Käuferprofil von diesem Tab entfernt. Wenn sie sich nicht angemeldet haben, befindet sich das Käuferprofil immer noch unter <b><span class="uicontrol"> Potenzielle Abonnenten</span></b>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Zugriff verweigert</span></b> </p> </td> 
   <td colname="col2"> <p>Führt abgelehnte Abonnementanforderungen für einen privaten Daten-Feed auf. </p> <p>Um abgelehnte Käufer erneut zu genehmigen, ändern Sie den <span class="wintitle"> Zurückweisungsstatus</span> in <b><span class="uicontrol"> Allow</span></b>. Dadurch wechselt der Käufer zu <b><span class="uicontrol"> Potenzielle Abonnenten</span></b>. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Nächste Schritte

Die folgende Dokumentation hilft Ihnen bei den ersten Schritten mit privaten Daten-Feeds.

* [Erstellen eines öffentlichen oder privaten Daten-Feeds](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed)
* [Private Feed-Anforderungen überprüfen, genehmigen oder ablehnen](../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests)
* [Private Daten-Feeds für Käufer](../../features/audience-marketplace/marketplace-private-feeds.md#private-data-feeds-for-buyers)

## Private Daten-Feeds für Käufer {#private-data-feeds-for-buyers}

Als Käufer erscheinen private Daten-Feeds in [Marketplace](../../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#about-marketplace) wie jedes andere Angebot. In diesem Fall zeigt die Feed-Liste jedoch keine Zusammenfassungsinformationen für Eigenschaften, Unique Users und Benutzerüberschneidungen an. Außerdem kann der Datenverkäufer seinen Namen in der Spalte [!UICONTROL Provider] der Liste [!UICONTROL Marketplace] anzeigen oder ausblenden. Nachdem der Verkäufer Ihre Abonnementanforderung genehmigt hat, stehen Ihnen alle Daten in einem privaten Feed zur Verfügung (sie funktionieren genau wie ein öffentlicher Feed). Im folgenden [!UICONTROL Marketplace]-Beispiel werden die drei verschiedenen Feed-Typen aufgelistet, die Ihnen als Käufer zur Verfügung stehen.

![](assets/buyer_marketplace.png)

Zu den Feed-Typen gehören:

In der Tabelle wird beschrieben, wie diese verschiedenen Feed-Typen Daten anzeigen oder ausblenden.

<table id="table_41D4A798ACF548A3A03ACB427CA4652D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feed-Typ </th> 
   <th colname="col2" class="entry"> Beschreibung </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Öffentlich</span></b> </p> </td> 
   <td colname="col2"> <p>Der Name, die Eigenschaft und die eindeutigen Daten des Providers werden in der Liste angezeigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Privat ohne Branding</span></b> </p> </td> 
   <td colname="col2"> <p>Der Name des Anbieters ist auf "Privater Verkäufer"festgelegt und Sie können Eigenschaftszahlen, eindeutige Daten und Daten zur Eigenschaftenüberlappung nicht sehen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Privat mit Branding</span></b> </p> </td> 
   <td colname="col2"> <p>Der Name des Anbieters wird in der Liste angezeigt, Sie können jedoch keine Daten zu Eigenschaftszahlen, eindeutigen Daten und Eigenschaftsüberschneidungen sehen. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Nächste Schritte

Siehe  [Abonnieren Sie ein Private Data ](../../features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed) Feedback , um Zugriff anzufordern.

## Einrichten der Sharing-Beziehung zwischen Datenanbieter und Datenkäufer {#set-up-sharing-relationship}

### Schritt 1: Aktivierung - Datenanbieter und Datenkäufer

Der erste Schritt in diesem Prozess erfordert ein Eingreifen von Adobe Consulting oder der Kundenunterstützung. Datenanbieter und Datenkäufer sollten sich an Adobe Consulting oder die Kundenunterstützung wenden, um die Aktivierung anzufordern.

### Schritt 2: Datenanbieter - Neue Datenquelle erstellen

Erstellen Sie in Ihrem Audience Manager-Konto eine neue Cookie-Datenquelle mit:

* **Audience Manager-** ID als eingehenden Schlüssel;
* Die Option **Freigeben aktiviert** ist aktiviert.

![](assets/create-datasource.png)

Nachdem Sie auf **Speichern** geklickt haben, wird automatisch ein neuer Unterordner unter **Eigenschaftsspeicher > Drittanbieterdaten** erstellt.

![](assets/folder-structure.png)

### Schritt 3: Datenanbieter - Eigenschaften für die Freigabe identifizieren

In diesem Schritt identifizieren Sie die Eigenschaften, die Sie für Ihren Partner freigeben möchten. Sie können entweder neue Eigenschaften erstellen oder vorhandene Eigenschaften bearbeiten. In jedem Fall benötigen Sie die Eigenschaften:

* Damit sie der Datenquelle zugeordnet werden können, die Sie im Rahmen von Schritt 2 erstellt haben.
* Im neu erstellten Unterordner unter Daten von Drittanbietern gespeichert werden.

Weitere Informationen zu [Erstellen von Eigenschaften](/help/using/features/traits/create-onboarded-rule-based-traits.md) und [Bearbeiten von Eigenschaften](/help/using/features/traits/manage-trait-rules.md#edit-trait).

### Schritt 4: Datenanbieter - Daten-Feed erstellen

Als Nächstes erstellen Sie einen Daten-Feed, um Ihre Eigenschaften mit dem Datenkäufer zu teilen. Anweisungen zum Erstellen eines Daten-Feeds finden Sie unter [Erstellen eines öffentlichen oder privaten Daten-Feeds](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md) .

>[!IMPORTANT]
>
>Wählen Sie in den Einstellungen die Option Privat aus. Wenn Sie dieses Feld auf &quot;Öffentlich&quot;setzen, kann jeder Audience Marketplace-Kunde Ihren Feed abonnieren.

![](assets/create-data-feed.png)

### 5. Schritt - Datenkäufer - Zugriff anfordern

Gehen Sie zu **Audience Marketplace > Marketplace**. Suchen Sie nach dem Daten-Feed, der vom Datenanbieter im vorherigen Schritt erstellt wurde. Klicken Sie auf **Zugriff anfordern**. Der von der Seite des Datenanbieters ausgewählte Kontakt erhält jetzt eine E-Mail-Benachrichtigung. Siehe auch [Einen privaten Daten-Feed abonnieren](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#subscript-private-data-feed).

### Schritt 6: Datenanbieter - Zugriff gewähren

Gehen Sie zu **Audience Marketplace > Meine freigegebenen Daten** und suchen Sie nach dem Feed, den Sie in Schritt 4 erstellt haben. Klicken Sie in die neue Zugriffsanfrage und klicken Sie auf **Zugriff zulassen** , um die Anfrage zu genehmigen. Siehe auch [Private Feed-Anforderungen überprüfen, genehmigen oder ablehnen](/help/using/features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#manage-private-requests).

### 7. Schritt - Datenkäufer - Abonnement aktivieren

Nachdem der Datenanbieter Zugriff auf den Daten-Feed gewährt hat, können Sie den Feed in Ihrem Konto unter **Audience Marketplace > Marketplace** sehen. Überprüfen Sie die Details, schalten Sie die Schaltfläche Anmeldung ein und klicken Sie auf **Überprüfen und abonnieren**. Informationen dazu, wo Sie die Eigenschaften von Drittanbietern finden, finden Sie unter [Speicher für abonnierte Daten-Feeds](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-manage-subscriptions.md#find-subscribed-data-fee).

Beachten Sie, dass diese Eigenschaften nur im Konto des Datenanbieters bearbeitet werden können.

---
description: Um Regeln für die Profilzusammenführung zu erstellen, überprüfen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Vorgehensweisen.
seo-description: Um Regeln für die Profilzusammenführung zu erstellen, überprüfen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Vorgehensweisen.
seo-title: Erste Schritte mit Profilzusammenführungsregeln
solution: Audience Manager
title: Erste Schritte mit Profilzusammenführungsregeln
uuid: 7 d 32 c 60 f -467 c -42 dd-afa 9-437 fd 7 c 473 c 5
translation-type: tm+mt
source-git-commit: c785c07a1572e9968e62a1bc753d24780eda64c5

---


# Erste Schritte mit Profilzusammenführungsregeln {#getting-started-with-profile-merge-rules}

Zum Erstellen [!UICONTROL Profile Merge Rules], Überprüfen und Ausführen der Schritte in den einzelnen in diesem Abschnitt beschriebenen Vorgehensweisen.

<!-- merge-rules-start.xml -->

## Geräteübergreifende Datenquelle erstellen {#create-data-source}

Um eine geräteübergreifende Datenquelle zu erstellen, gehen **[!UICONTROL Audience Data > Data Sources > Add New]** Sie zu den Schritten, die Sie hier beschrieben haben. Zum Erstellen oder Bearbeiten einer geräteübergreifenden Datenquelle sind Administratorrechte erforderlich.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Beschreibungen dieser verschiedenen Steuerelemente finden Sie unter [Datenquelleneinstellungen und Menüoptionen](../../features/datasources-list-and-settings.md#settings-menu-options) .

## Datenquellendetails {#details}

So füllen Sie den [!UICONTROL Data Source Details] Abschnitt aus:

1. Benennen Sie die Datenquelle.
1. *(Optional)* Beschreiben Sie die Datenquelle. Eine knappe Beschreibung hilft Ihnen, die Rolle oder den Zweck der Datenquelle zu definieren.
1. Geben Sie einen Integrationscode an. Ein Integrationscode ist Ihre eigene eindeutige ID für diese Datenquelle.
1. Wählen Sie in der **[!UICONTROL ID Type]** Liste **[!UICONTROL Cross Device]** den Eintrag.
1. Wählen Sie in der **[!UICONTROL ID Definition]** Liste eine Option aus, die den Datenquellentyp definiert. Zu den Optionen zählen:
   * **[!UICONTROL Person]**: Eine ID, die eine einzelne Person definiert. Diese ID kann mehreren [!DNL Audience Manager] IDs zugeordnet werden.
   * **[!UICONTROL Household]**: Eine ID, die eine Gruppe von Personen definiert. Diese ID kann mehreren [!DNL Audience Manager] IDs zugeordnet werden.

## Datenexportkontrolle {#export-controls}

[Datenexportsteuerelemente](../../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine Datenquelle und ein Ziel anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion einen Datenschutz verletzt oder Vereinbarung verwendet. Überspringen Sie diesen Abschnitt, wenn Sie nicht verwenden [!UICONTROL Data Export Controls].

## Datenquelleneinstellungen {#settings}

[!UICONTROL Data Source Settings] enthält mehrere Optionen, diese beiden sind jedoch für die Erstellung einer geräteübergreifenden Datenquelle wichtig:

* **[!UICONTROL Use as Authenticated Profile]**: Mit dieser Einstellung können Sie standardmäßig eine [!UICONTROL Profile Merge Rule] mit Ihren eigenen, authentifizierten Daten erstellen.

* **[!UICONTROL Use as a Device Graph]**: Dieses Steuerelement ist nur für Konten verfügbar, die als Datenanbieter aufgeführt sind. Durch Auswahl dieses Kontrollkästchens wird Ihre Datenquelle als Gerätediagramm erstellt und für andere [!DNL Audience Manager] Kunden freigegeben. Arbeiten Sie mit Ihrem [!DNL Audience Manager] Berater zusammen, um als Datenanbieter einzurichten und anzugeben, für welche Kunden dieser [!UICONTROL Data Source] freigegeben werden soll. Ihr Berater stellt Ihr Konto und Ihre Gerätediagrammfreigabe über interne Bereitstellungsprozesse bereit.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Mit diesem Steuerelement können Sie die Datenaufbewahrungsdauer für inaktive Kunden-IDs festlegen. Dies legt fest, wie lange Audience Manager Kunden-IDs in unserer Datenbank beibehält, nachdem sie zuletzt auf der Audience Manager-Plattform gesehen wurden. Der Standardwert ist 24 Monate (720 Tage). Der Mindestwert, den Sie einstellen können, beträgt 1 Monat und der Höchstwert 5 Jahre. Beachten Sie, dass wir alle Monate als 30 Tage zählen. Audience Manager führt einen Prozess, der inaktive Kunden-IDs einmal wöchentlich löscht, gemäß der Datenaufbewahrung aus, die Sie für inaktive Kunden-IDs festgelegt haben.

Mit den mit diesen Einstellungen verknüpften Textfeldern können Sie den Namen [!UICONTROL Data Source] eines Alias umbenennen, der in den Optionen für [die Profilzusammenführung angezeigt](../../features/profile-merge-rules/merge-rule-definitions.md)wird. Wenn Sie zum **[!UICONTROL Use as Authenticated Profile]** Beispiel einen Alias hinzufügen, wird dieser Name in der [!UICONTROL Authenticated Profile Options] Liste angezeigt. Wenn Sie einen Alias hinzufügen, **[!UICONTROL Use as a Device Graph]** wird dieser Name in der [!UICONTROL Device Options] Liste angezeigt.

>[!MORE_ LIKE_ THIS]
>
>* [Datenquelle erstellen](../../features/manage-datasources.md#create-data-source)


## Regel für die Profilzusammenführung erstellen {#create-profile-merge-rule}

Gehen Sie zum Erstellen von Schritten [!UICONTROL Profile Merge Rule]**[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** zu den Schritten, die hier beschrieben werden. Sie können bis zu 3 Zusammenführungsregeln erstellen, nachdem Sie eine geräteübergreifende Datenquelle eingerichtet haben. Zum Erstellen, Bearbeiten oder Löschen einer Regel sind Administratorrechte erforderlich. Alle Benutzer können vorhandene [!UICONTROL Profile Merge Rules]anzeigen und verwenden.

<!-- create-profile-merge-rule.xml -->

**Voraussetzungen:** Zum Erstellen einer [!UICONTROL Profile Merge Rule]Datei ist eine geräteübergreifende Datenquelle erforderlich. Siehe [Erstellen einer Datenquelle](../../features/manage-datasources.md#create-data-source).

>[!TIP]
>
>See [Profile Merge Rule Options Defined](../../features/profile-merge-rules/merge-rule-definitions.md) for descriptions of these different controls.

## Basisinformationen {#basic-info}

So füllen Sie den [!UICONTROL Basic Information] Abschnitt aus:

1. Benennen [!UICONTROL Profile Merge Rule]Sie den.
2. *(Optional)* Beschreiben Sie die [!UICONTROL Profile Merge Rule]. Eine knappe Beschreibung hilft Ihnen, die Rolle oder den Zweck Ihrer Regel zu definieren.
3. *(Optional)* Wählen **[!UICONTROL Set as default]** Sie diese Option aus, wenn Sie diese Einstellung als Standard [!UICONTROL Profile Merge Rule]festlegen möchten. Neue Segmente werden automatisch mit der Standardregel verknüpft.

## Datenexportkontrolle {#data-export-controls}

[Die Datenexportsteuerelemente](../../features/data-export-controls.md) sind optionale Classification-Regeln, die Sie auf Ihre [!UICONTROL Profile Merge Rule]anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion einen Datenschutz verletzt oder Vereinbarung verwendet. Überspringen Sie diesen Abschnitt, wenn Sie nicht verwenden [!UICONTROL Data Export Controls].

## Regeleinrichtung für Profilzusammenführung {#profile-merge-rule-setup}

So füllen Sie den [!UICONTROL Proflie Merge Rule Setup] Abschnitt aus:

1. Wählen Sie eine **[!UICONTROL Authenticated Option]**. Zu den Optionen zählen:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Wählen Sie eine **[!UICONTROL Authenticated Profile Option]** (bis zu 3, maximal). Dies sind [die geräteübergreifenden Datenquellen, die](../../features/profile-merge-rules/merge-rules-start.md) Sie zuvor erstellt haben.
3. Wählen Sie eine **[!UICONTROL Device Option]**. Zu den Optionen zählen:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Klicken Sie auf **[!UICONTROL Save]**.

## Konfigurieren von Regelcode für Zusammenführungsregeln {#configure-merge-rule-code}

Befolgen Sie diese Anweisungen, um den Code [!UICONTROL Experience Cloud ID Service]und [!UICONTROL DIL]den Mobilcode [!DNL SDK] für die Verwendung mit Ihren Zusammenführungsregeln einzurichten.

<!-- merge-rules-configure-code.xml -->

### Voraussetzungen

Vor Abschluss dieser Verfahren müssen Sie eine [geräteübergreifende Datenquelle](#create-data-source) und [Regeln](#create-profile-merge-rule) *für die Profilzusammenführung* einrichten.

## Für Experience Cloud ID-Dienstkunden {#id-service-customers}

Die und [!UICONTROL Experience Cloud ID Service] die aktuelle Version von [DIL](../../dil/dil-overview.md) werden bei der Arbeit mit [!UICONTROL Profile Merge Rules]Ihnen empfohlen. Sie müssen jedoch nicht mit [!UICONTROL Experience Cloud ID Service] dieser Funktion arbeiten. Wenn Sie nur dazu verwenden [!UICONTROL DIL], lesen Sie den [unten stehenden](../../features/profile-merge-rules/merge-rules-start.md#legacy-dil) Abschnitt zu DIL.

### Funktion &quot;Kunden-ID festlegen&quot; konfigurieren

Wenn Sie mit der [!UICONTROL Experience Cloud ID Service]Funktion arbeiten, übergibt die `setCustomerIDs` Funktion deklarierte IDs an [!DNL Audience Manager]. Um eine Regel zum Zusammenführen von Profilen zu verwenden, müssen Sie den `setCustomerIDs` Integrationscode ändern, der angegeben wurde, wenn Sie eine geräteübergreifende Datenquelle erstellt haben. Angenommen, Sie haben eine geräteübergreifende Datenquelle mit dem Integrationscode `my_datasource_ic`erstellt. Um eine deklarierte ID zu übermitteln, fügen Sie den Integrationscode der Besucher-ID-Funktion hinzu, wie im folgenden Codebeispiel unten gezeigt.

#### Generisches Codebeispiel

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### Beispiel für ein Codebeispiel

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

Weitere Informationen finden Sie unter [Erstellen einer geräteübergreifenden Datenquelle](#create-data-source) sowie [Kunden-IDs und Authentifizierungsstatus](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_customer_ids.html).

### `DIL.create` Funktion konfigurieren

Die neuesten Versionen [!UICONTROL DIL] beziehen sich jetzt automatisch [!UICONTROL declared ID] von der `visitorService` Funktion in `DIL.create` (siehe [Deklarierte ID-Variablen](../../features/declared-ids.md#declared-id-variables)). Überprüfen Sie Ihre `DIL.create` Funktion, um sicherzustellen, dass diese korrekt eingerichtet ist, wie im Codebeispiel unten dargestellt.

<pre class="js"><code>var vdil = DIL. create ({partner: " Name des Partners ",
 visitorservice: {namespace: "<i>INSERT-MCORG-ID-HERE</i>"}});</code>
</pre>

Im Namespace-Schlüssel-Wert-Paar ist die `*`MCORG`*` -Variable Ihre [!DNL Experience Cloud] Organisations-ID. Wenn Sie diese ID nicht haben, können Sie sie im [!UICONTROL Administration][!DNL Experience Cloud] Dashboard finden. Sie benötigen Administratorrechte, um dieses Dashboard anzuzeigen. Siehe [Administration: Hauptdienste](https://marketing.adobe.com/resources/help/en_US/mcloud/?f=admin_getting_started.html).

### Sdks konfigurieren

Siehe [Abschnitt &quot;sdks](../../features/profile-merge-rules/merge-rules-start.md#configure-sdks) konfigurieren&quot; .

## Legacy-DIL {#legacy-dil}

Sollten Sie noch nicht verwenden [!DNL Experience Cloud ID Service] , sollten Sie es eigentlich tun. Wir wissen jedoch, dass der Wechsel zu neuen Code sorgfältig durchdacht und getestet werden muss. Überprüfen Sie in diesen Fällen, `DIL.create` ob diese korrekt eingerichtet ist, wie im Codebeispiel unten dargestellt.

<pre class="js"><code>DIL. create ({partner: " partnername ",
 declaredid: {dpuuid:<i>dpuuid</i>,
 dpid:<i>dpid</i>}});</code>
</pre>

Weitere Informationen finden Sie im Abschnitt zu [!UICONTROL DIL][deklarierten ID-Variablen](../../features/declared-ids.md#declared-id-variables).

### Sdks konfigurieren {#configure-sdks-legacy-dil}

Überprüfen Sie die Methoden in Ihrem [!DNL SDK] Code, über die Sie die Weitergabe [!UICONTROL declared IDs] von [!DNL Android][!DNL iOS] Mobilgeräten durchführen können. Die Variablennamen für die Bibliotheken [!DNL Android] und [!DNL iOS] Codebibliotheken sind identisch:

* `dpid`: Die geräteübergreifende Datenquellen-ID.
* `dpuuid`: Das [!UICONTROL declared ID] (d. h. die Benutzer-ID).

<table id="table_2ACA3E5F316D4413B10A4403B786CC23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gerätetyp </th> 
   <th colname="col2" class="entry"> Methode </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b> Android </b> </p> </td> 
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Syntax:</b> </p> <p> <pre> public static void setdpidanddpuuid (String dpid, String dpuuid); </pre> </p> <p> <b>Beispiel:</b> </p> <p> <pre> Audiencemanager. setdpidanddpuuid ("mydpid", "mydpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> Audiencesetdpid: dpuuid </code> </p> <p> <b>Syntax:</b> </p><p>
    <code class="javascript">+ (void) audiencesetdpid: (Nsstring *) dpid 
 dpuuid: (Nsstring *) dpuuid; </code>
 </p>
    <p> <b>Beispiel:</b> </p><p>
    <code class="javascript">[Adbmobile audiencesetdpid: @ "290" dpuuid: @ "99301393923940"]; </code>
 </p>
    </td>
  </tr>
 </tbody>
</table>

Weitere Informationen finden Sie unter [Audience Manager-Methoden für Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=c_audience_manager_methods.html) und [Audience Manager-Methoden für ios](https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=aam_methods.html).

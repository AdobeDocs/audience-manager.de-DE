---
description: Um Profil Merge Rules zu erstellen, überprüfen und führen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Verfahren aus.
seo-description: Um Profil Merge Rules zu erstellen, überprüfen und führen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Verfahren aus.
seo-title: Erste Schritte mit Profilzusammenführungsrichtlinien
solution: Audience Manager
title: Erste Schritte mit Profilzusammenführungsrichtlinien
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1306'
ht-degree: 4%

---

# Erste Schritte mit Profilzusammenführungsrichtlinien {#getting-started-with-profile-merge-rules}

Um [!UICONTROL Profile Merge Rules] zu erstellen, überprüfen und führen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Verfahren aus.

<!-- merge-rules-start.xml -->

## Eine geräteübergreifende Datenquelle {#create-data-source} erstellen

Um eine geräteübergreifende Datenquelle zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Data Sources > Add New]** und führen Sie die Schritte für jeden Abschnitt durch, der hier beschrieben wird. Zum Erstellen oder Bearbeiten einer geräteübergreifenden Datenquelle sind Administratorberechtigungen erforderlich.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Beschreibungen dieser verschiedenen Steuerelemente finden Sie unter [Datenquelleneinstellungen und Menüoptionen](../datasources-list-and-settings.md#settings-menu-options).

## Datenquellendetails {#details}

So füllen Sie den Abschnitt [!UICONTROL Data Source Details] aus:

1. Benennen Sie die Datenquelle.
2. *(Optional)* Beschreiben Sie die Datenquelle. Eine knappe Beschreibung hilft Ihnen, die Rolle oder den Zweck der Datenquelle zu definieren.
3. Geben Sie einen Integrationscode ein. Ein Integrationscode ist Ihre eigene eindeutige ID für diese Datenquelle.
4. Wählen Sie in der Liste **[!UICONTROL ID Type]** **[!UICONTROL Cross Device]**.
5. Wählen Sie in der Liste **[!UICONTROL ID Definition]** eine Option, die den Datenquellentyp definiert. Zu den Optionen zählen:
   * **[!UICONTROL Person]**: Eine ID, die eine einzelne Person definiert. Diese ID kann mehreren [!DNL Audience Manager]-IDs zugeordnet werden.
   * **[!UICONTROL Household]**: Eine ID, die eine Gruppe von Personen definiert. Diese ID kann mehreren [!DNL Audience Manager]-IDs zugeordnet werden.

## Datenexportkontrollen {#export-controls}

[Datenexport-](../data-export-controls.md) Steuerelemente sind optionale Classification-Regeln, die Sie auf eine Datenquelle und ein Ziel anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls] nicht verwenden.

## Datenquelleneinstellungen {#settings}

[!UICONTROL Data Source Settings] bietet mehrere Optionen, diese beiden sind jedoch wichtig für die Erstellung einer geräteübergreifenden Datenquelle:

* **[!UICONTROL Use as Authenticated Profile]**: Diese Einstellung ist standardmäßig aktiviert und ermöglicht es Ihnen, eine  [!UICONTROL Profile Merge Rule] mit Ihren eigenen, authentifizierten Daten zu erstellen.

* **[!UICONTROL Use as a Device Graph]**: Dieses Steuerelement steht nur für Konten zur Verfügung, die als Datenanbieter aufgeführt sind. Wenn Sie dieses Kontrollkästchen aktivieren, wird Ihre Datenquelle als Gerätediagramm erstellt und Sie können sie für andere [!DNL Audience Manager]-Kunden freigeben. Wenden Sie sich an Ihren [!DNL Audience Manager]-Berater, um sich als Datenanbieter einzurichten und anzugeben, für welche Kunden dieses [!UICONTROL Data Source] freigegeben werden soll. Ihr Berater stellt Ihre Konto- und Gerätediagrammfreigabe über interne Bereitstellungsprozesse bereit.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Mit diesem Steuerelement können Sie die Datenaufbewahrungszeit für inaktive Kunden-IDs festlegen. Dadurch wird bestimmt, wie lange Audience Manager Kunden-IDs in unserer Datenbank aufbewahren, nachdem sie zuletzt auf der Audience Manager-Plattform gesehen wurden. Der Standardwert ist 24 Monate (720 Tage). Der Mindestwert, den Sie einstellen können, ist 1 Monat und der Höchstwert 5 Jahre. Beachten Sie, dass wir alle Monate als 30 Tage zählen. Audience Manager führt einen Prozess aus, bei dem inaktive Kunden-IDs einmal wöchentlich gelöscht werden, entsprechend der für inaktive Kunden-IDs festgelegten Datenaufbewahrung.

Mit den mit diesen Einstellungen verknüpften Textfeldern können Sie [!UICONTROL Data Source] mit einem Alias umbenennen, der in den Optionen [Profil Merge Rule ](merge-rule-definitions.md) angezeigt wird. Wenn Sie beispielsweise **[!UICONTROL Use as Authenticated Profile]** einen Alias hinzufügen, wird dieser Name in der Liste [!UICONTROL Authenticated Profile Options] angezeigt. Wenn Sie **[!UICONTROL Use as a Device Graph]** einen Alias hinzufügen, wird dieser Name in der Liste [!UICONTROL Device Options] angezeigt.

## Eine Profil Merge Rule {#create-profile-merge-rule} erstellen

Um ein [!UICONTROL Profile Merge Rule] zu erstellen, gehen Sie zu **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** und führen Sie die Schritte für jeden Abschnitt durch, der hier beschrieben wird.

Sie können bis zu 3 Zusammenführungsregeln erstellen, nachdem Sie eine geräteübergreifende Datenquelle eingerichtet haben. Sie erhalten Zugriff auf eine 4. Profil-Merge-Regel ([!UICONTROL All Cross-Device Profiles]), wenn Sie sich für [Benutzerbasierte Ziele](../destinations/people-based-destinations-overview.md) registrieren.

Zum Erstellen, Bearbeiten oder Löschen einer Regel sind Administratorberechtigungen erforderlich. Alle Benutzer können bestehende [!UICONTROL Profile Merge Rules] Ansicht und verwenden.

<!-- create-profile-merge-rule.xml -->

**Voraussetzungen:** Eine geräteübergreifende Datenquelle ist erforderlich, um eine  [!UICONTROL Profile Merge Rule]zu erstellen. Siehe [Datenquelle erstellen](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Beschreibungen dieser verschiedenen Steuerelemente finden Sie unter [Profil Merge Rule Options Defined](merge-rule-definitions.md).

## Basisinformationen {#basic-info}

So füllen Sie den Abschnitt [!UICONTROL Basic Information] aus:

1. Benennen Sie [!UICONTROL Profile Merge Rule].
2. *(Optional)* Beschreiben Sie die  [!UICONTROL Profile Merge Rule]. Eine kurze Beschreibung hilft Ihnen, die Rolle oder den Zweck Ihrer Regel zu definieren.
3. *(Optional)* Wählen Sie  **[!UICONTROL Set as default]** diese Option aus, wenn Sie dies als Standard festlegen möchten  [!UICONTROL Profile Merge Rule]. Neue Segmente werden automatisch mit der Standardregel verknüpft.

## Datenexportkontrollen {#data-export-controls}

[Datenexport-](../data-export-controls.md) Steuerelemente sind optionale Classification-Regeln, die Sie auf Ihre  [!UICONTROL Profile Merge Rule]Anwendung anwenden können. Sie verhindern, dass Sie Daten an ein Ziel senden, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls] nicht verwenden.

## Profil Merge Rule Setup {#profile-merge-rule-setup}

So füllen Sie den Abschnitt [!UICONTROL Proflie Merge Rule Setup] aus:

1. Wählen Sie ein **[!UICONTROL Authenticated Option]**. Zu den Optionen zählen:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Wählen Sie ein **[!UICONTROL Authenticated Profile Option]** (maximal 3). Dies sind die [geräteübergreifenden Datenquellen](merge-rules-start.md), die Sie zuvor erstellt haben.
3. Wählen Sie eine **[!UICONTROL Device Option]**. Zu den Optionen zählen:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
   * **[!UICONTROL Device Co-op]**
4. Klicken **[!UICONTROL Save]**.

### Überlegungen zu Adobe Campaign-Zielen mit geräteübergreifenden IDs als Benutzer-ID-Schlüssel {#considerations}

Ende 2019 haben wir eine Reihe von Profil Merge Rules Erweiterungen veröffentlicht, um die Genauigkeit von Batch-Dateien zu verbessern, die mit geräteübergreifenden IDs generiert wurden. Diese Verbesserungen werden in Ihrer Audience Manager-Instanz ab Montag, dem 16. März 2020 strikt berücksichtigt. Segmente, die einem Ziel mit geräteübergreifenden IDs zugeordnet sind, produzieren daher in einigen Profil Merge Rules Konfigurationen keine Exporte mehr.

Um die richtige Integration zwischen Ihrer Audience Manager-Instanz und Zielen mithilfe geräteübergreifender IDs, z. B. Adobe Campaign, sicherzustellen, stellen Sie sicher, dass folgende Anforderungen erfüllt sind:

1. Überprüfen Sie die Segmentzusammenführungsregel, die von den Segmenten verwendet wird, die Ihrem Adobe Campaign Deklarierte ID-Ziel zugeordnet sind. Die Profil Merge-Regel muss die Option [!UICONTROL Last Authenticated Profile] verwenden, damit alle authentifizierten Profil in die Exporte einbezogen werden können. Wenn Ihre Profil Merge Rule eine andere Option verwendet, wechseln Sie zu [!UICONTROL Last Authenticated Profile].
2. Wählen Sie in den Einstellungen für die Profil-Zusammenführungsregel die Datenquelle für das Adobe Campaign Deklariert aus.

>[!NOTE]
>
> Wenn Sie die maximale Anzahl von [!UICONTROL Profile Merge Rules] erreicht haben und Hilfe bei der Konfiguration benötigen, wie oben beschrieben, wenden Sie sich bitte an den Kundendienst.

## Konfigurieren des Merge Rule Code {#configure-merge-rule-code}

Führen Sie die folgenden Anweisungen aus, um den [!UICONTROL Adobe Experience Platform Identity Service]-, [!UICONTROL DIL]- und Mobilcode [!DNL SDK]-Code für die Verwendung mit Ihren Zusammenführungsregeln einzurichten.

<!-- merge-rules-configure-code.xml -->

### Voraussetzungen

Sie müssen eine [geräteübergreifende Datenquelle](#create-data-source) und [Profil Mergeregeln](#create-profile-merge-rule) *einrichten, bevor Sie diese Verfahren abschließen.*

## Für Adobe Experience Platform Identity Service Customers {#id-service-customers}

Die [!UICONTROL Adobe Experience Platform Identity Service] und die neueste Version von [DIL](../../dil/dil-overview.md) werden beim Arbeiten mit [!UICONTROL Profile Merge Rules] empfohlen. Sie müssen jedoch nicht [!UICONTROL Adobe Experience Platform Identity Service] verwenden, um mit dieser Funktion zu arbeiten. Wenn Sie nur [!UICONTROL DIL] verwenden, lesen Sie den Abschnitt [Legacy-DIL](#legacy-dil) weiter unten.

### Konfigurieren der Funktion &quot;Kunden-ID festlegen&quot;

Beim Arbeiten mit [!UICONTROL Adobe Experience Platform Identity Service] übergibt die Funktion `setCustomerIDs` deklarierte IDs an [!DNL Audience Manager]. Um eine Profil Merge-Regel zu verwenden, müssen Sie `setCustomerIDs` ändern, um den Integrationscode zu verwenden, der beim Erstellen einer geräteübergreifenden Datenquelle angegeben wurde. Angenommen, Sie haben eine geräteübergreifende Datenquelle mit dem Integrationscode `my_datasource_ic` erstellt. Um eine deklarierte ID zu übergeben, fügen Sie den Integrationscode zur Besucher-ID-Funktion hinzu, wie im folgenden Codebeispiel für Änderungen dargestellt.

#### Beispiel für generischen Code

```javascript
visitor.setCustomerIDs({
  "userid":{
      "id":"12345",
      "authState":Visitor.AuthState.AUTHENTICATED
```

#### Muster für modifizierten Code

```javascript
visitor.setCustomerIDs({
  "my_datasource_ic":{
     "id":"12345",
     "authState":Visitor.AuthState.AUTHENTICATED
```

Weitere Informationen finden Sie unter [Erstellen einer geräteübergreifenden Datenquelle](#create-data-source) und [Kunden-IDs und Authentifizierungsstatus](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html).

### Funktion `DIL.create` konfigurieren

Die neuesten Versionen von [!UICONTROL DIL] übernehmen nun automatisch die Funktion [!UICONTROL declared ID] von `visitorService` in `DIL.create` (siehe [Deklarierte ID-Variablen](../declared-ids.md#declared-id-variables)). Überprüfen Sie Ihre `DIL.create`-Funktion, um sicherzustellen, dass diese korrekt eingerichtet ist, wie im folgenden Codebeispiel dargestellt.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Im Schlüssel-Wert-Paar des Namensraums ist die Variable `*`MCORG`*` Ihre [!DNL Experience Cloud]-Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im Abschnitt [!UICONTROL Administration] des [!DNL Experience Cloud]-Dashboards. Sie benötigen Administratorrechte, um dieses Dashboard Ansicht. Siehe [Administration: Hauptdienste](https://docs.adobe.com/content/help/de-DE/core-services/interface/manage-users-and-products/admin-getting-started.html).

### SDKs konfigurieren

Siehe Abschnitt [SDKs konfigurieren](#configure-sdks-legacy-dil).

## Legacy-DIL {#legacy-dil}

Wenn Sie [!DNL Adobe Experience Platform Identity Service] noch nicht verwenden, sollten Sie das wirklich tun. Aber wir verstehen, dass die Umstellung auf neuen Code sorgfältige Überlegungen und Tests erfordert. Überprüfen Sie in diesen Fällen Ihre `DIL.create`-Funktion, um sicherzustellen, dass diese korrekt eingerichtet ist, wie im folgenden Codebeispiel dargestellt.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Weitere Informationen finden Sie im Abschnitt [!UICONTROL DIL] im Abschnitt [Deklarierte ID-Variablen](../declared-ids.md#declared-id-variables).

### SDKs {#configure-sdks-legacy-dil} konfigurieren

Überprüfen Sie die Methoden im [!DNL SDK]-Code, mit denen Sie [!UICONTROL declared IDs] von [!DNL Android]- und [!DNL iOS]-Mobilgeräten übergeben können. Die Variablennamen für die Codebibliotheken [!DNL Android] und [!DNL iOS] sind identisch:

* `dpid`: Die geräteübergreifende Datenquellen-ID.
* `dpuuid`: Die  [!UICONTROL declared ID] (d. h. die Benutzer-ID).

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
   <td colname="col2"> <p> <code> setDpidAndDpuuid </code> </p> <p> <b>Syntax:</b> </p> <p> <pre> public static void setDpidAndDpuuid(String dpid, String dpuuid); </pre> </p> <p> <b>Beispiel:</b> </p> <p> <pre> AudienceManager.setDpidAndDpuuid("myDpid","myDpuuid"); </pre> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> iOS </b> </p> </td> 
   <td colname="col2"> <p> <code> audienceSetDpid:dpuuid </code> </p> <p> <b>Syntax:</b> </p><p>
    <code class="javascript">
      +&nbsp;(void)&nbsp;audienceSetDpid:(NSString&nbsp;*)dpid 
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:(NSString&nbsp;*)dpuuid; 
    </code></p>
    <p> <b>Beispiel:</b> </p><p>
    <code class="javascript">
      [ADBMobile&nbsp;audienceSetDpid:@"290"
      &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;dpuuid:@"99301393923940"];
    </code></p>
    </td>
  </tr>
 </tbody>
</table>

Siehe auch [Audience Manager-Methoden für Android](hhttps://docs.adobe.com/content/help/en/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) und [Audience Manager-Methoden für iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Erstellen einer Datenquelle](../manage-datasources.md#create-data-source)


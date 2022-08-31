---
description: Um Profilzusammenführungsrichtlinien zu erstellen, überprüfen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Verfahren und führen Sie sie aus.
seo-description: To create Profile Merge Rules review and complete the steps in each of the procedures described in this section.
seo-title: Getting Started with Profile Merge Rules
solution: Audience Manager
title: Erste Schritte mit Profilzusammenführungsrichtlinien
uuid: 7d32c60f-467c-42dd-afa9-437fd7c473c5
feature: Profile Merge
exl-id: 11f397dd-1f23-4b14-be6f-60ce8b77ab12
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1280'
ht-degree: 3%

---

# Erste Schritte mit Profilzusammenführungsrichtlinien {#getting-started-with-profile-merge-rules}

Erstellen [!UICONTROL Profile Merge Rules], überprüfen und führen Sie die Schritte in den einzelnen in diesem Abschnitt beschriebenen Verfahren aus.

<!-- merge-rules-start.xml -->

## Geräteübergreifende Datenquelle erstellen {#create-data-source}

Um eine geräteübergreifende Datenquelle zu erstellen, navigieren Sie zu **[!UICONTROL Audience Data > Data Sources > Add New]** und führen Sie die Schritte für jeden Abschnitt aus, der hier beschrieben wird. Zum Erstellen oder Bearbeiten einer geräteübergreifenden Datenquelle sind Administratorberechtigungen erforderlich.

<!-- create-cross-device-datasource.xml -->

>[!TIP]
>
>Siehe [Datenquelleneinstellungen und Menüoptionen](../datasources-list-and-settings.md#settings-menu-options) für Beschreibungen dieser verschiedenen Steuerelemente.

## Datenquellendetails {#details}

So schließen Sie die [!UICONTROL Data Source Details] Abschnitt:

1. Benennen Sie die Datenquelle.
2. *(Optional)* Beschreiben Sie die Datenquelle. Eine kurze Beschreibung hilft Ihnen bei der Definition der Rolle oder des Zwecks der Datenquelle.
3. Geben Sie einen Integrationscode an. Ein Integrationscode ist Ihre eigene eindeutige ID für diese Datenquelle.
4. Im **[!UICONTROL ID Type]** Liste auswählen **[!UICONTROL Cross Device]**.
5. Im **[!UICONTROL ID Definition]** auswählen, wählen Sie eine Option, die den Datenquellentyp definiert. Zu den Optionen zählen:
   * **[!UICONTROL Person]**: Eine ID, die eine einzelne Person definiert. Diese ID kann mehreren [!DNL Audience Manager] IDs.
   * **[!UICONTROL Household]**: Eine ID, die eine Gruppe von Personen definiert. Diese ID kann mehreren [!DNL Audience Manager] IDs.

## Datenexportkontrollen {#export-controls}

[Datenexportkontrollen](../data-export-controls.md) sind optionale Classification-Regeln, die Sie auf eine Datenquelle und ein Ziel anwenden können. Sie verhindern das Senden von Daten an ein Ziel, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls].

## Datenquelleneinstellungen {#settings}

[!UICONTROL Data Source Settings] -Abschnitt bietet mehrere Optionen, diese beiden sind jedoch für die Erstellung einer geräteübergreifenden Datenquelle wichtig:

* **[!UICONTROL Use as Authenticated Profile]**: Diese standardmäßig ausgewählte Einstellung ermöglicht den Aufbau einer [!UICONTROL Profile Merge Rule] mit Ihren eigenen, authentifizierten Daten.

* **[!UICONTROL Use as a Device Graph]**: Dieses Steuerelement ist nur für Konten verfügbar, die als Datenanbieter aufgeführt sind. Wenn Sie dieses Kontrollkästchen aktivieren, wird Ihre Datenquelle als Gerätediagramm erstellt und Sie können sie für andere freigeben [!DNL Audience Manager] -Kunden. Arbeiten mit [!DNL Audience Manager] Berater, um als Datenanbieter einzurichten und anzugeben, welche Kunden dies tun [!UICONTROL Data Source] sollte für freigegeben werden. Ihr Berater stellt Ihre Freigabe von Konten und Gerätediagrammen über interne Bereitstellungsprozesse bereit.

* **[!UICONTROL Data retention for inactive Customer IDs]**: Mit dieser Steuerung können Sie die Datenaufbewahrungsdauer für inaktive Kunden-IDs festlegen. Dadurch wird bestimmt, wie lange der Audience Manager Kunden-IDs in unserer Datenbank aufbewahrt, nachdem sie zuletzt auf der Audience Manager-Plattform angezeigt wurden. Der Standardwert ist 24 Monate (720 Tage). Der Mindestwert, den Sie einstellen können, ist 1 Monat und der Höchstwert 5 Jahre. Beachten Sie, dass wir alle Monate als 30 Tage zählen. Audience Manager führt einen Prozess aus, der inaktive Kunden-IDs einmal wöchentlich löscht. Dies entspricht der Datenaufbewahrung, die Sie für inaktive Kunden-IDs festgelegt haben.

Mit den mit diesen Einstellungen verknüpften Textfeldern können Sie die [!UICONTROL Data Source] mit einem Alias, der im [Optionen für Profilzusammenführungsregeln](merge-rule-definitions.md). Wenn Sie beispielsweise einen Alias zu **[!UICONTROL Use as Authenticated Profile]**, wird dieser Name in der [!UICONTROL Authenticated Profile Options] Liste. Wenn Sie einen Alias zu **[!UICONTROL Use as a Device Graph]**, wird dieser Name in der [!UICONTROL Device Options] Liste.

## Erstellen einer Profilzusammenführungsrichtlinie {#create-profile-merge-rule}

So erstellen Sie eine [!UICONTROL Profile Merge Rule], gehen Sie zu **[!UICONTROL Audience Data > Profile Merge Rules > Add New Rule]** und führen Sie die Schritte für jeden Abschnitt aus, der hier beschrieben wird.

Sie können bis zu 3 Zusammenführungsregeln erstellen, nachdem Sie eine geräteübergreifende Datenquelle eingerichtet haben. Sie erhalten Zugriff auf eine vierte Profilzusammenführungsrichtlinie ([!UICONTROL All Cross-Device Profiles]), wenn Sie sich für [Benutzerbasierte Ziele](../destinations/people-based-destinations-overview.md).

Zum Erstellen, Bearbeiten oder Löschen einer Regel sind Administratorberechtigungen erforderlich. Alle Benutzer können vorhandene [!UICONTROL Profile Merge Rules].

<!-- create-profile-merge-rule.xml -->

**Voraussetzungen:** Zum Erstellen einer [!UICONTROL Profile Merge Rule]. Siehe [Erstellen einer Datenquelle](../manage-datasources.md#create-data-source).

>[!TIP]
>
>Siehe [Definierte Optionen für Profilzusammenführungsregeln](merge-rule-definitions.md) für Beschreibungen dieser verschiedenen Steuerelemente.

## Basisinformationen {#basic-info}

So schließen Sie die [!UICONTROL Basic Information] Abschnitt:

1. Benennen Sie die [!UICONTROL Profile Merge Rule].
2. *(Optional)* Beschreiben Sie die [!UICONTROL Profile Merge Rule]. Eine kurze Beschreibung hilft Ihnen bei der Definition der Rolle oder des Zwecks Ihrer Regel.
3. *(Optional)* Auswählen **[!UICONTROL Set as default]** , wenn Sie dies zur Standardeinstellung machen möchten [!UICONTROL Profile Merge Rule]. Neue Segmente werden automatisch mit der Standardregel verknüpft.

## Datenexportkontrollen {#data-export-controls}

[Datenexportkontrollen](../data-export-controls.md) sind optionale Classification-Regeln, die auf Ihre [!UICONTROL Profile Merge Rule]. Sie verhindern das Senden von Daten an ein Ziel, wenn diese Aktion gegen eine Datenschutz- oder Nutzungsvereinbarung verstößt. Überspringen Sie diesen Abschnitt, wenn Sie [!UICONTROL Data Export Controls].

## Einrichten von Profilzusammenführungsregeln {#profile-merge-rule-setup}

So schließen Sie die [!UICONTROL Proflie Merge Rule Setup] Abschnitt:

1. Wählen Sie eine **[!UICONTROL Authenticated Option]**. Zu den Optionen zählen:
   * **[!UICONTROL No Authenticated Profile]**
   * **[!UICONTROL Current Authenticated Profile]**
   * **[!UICONTROL Last Authenticated Profile]**
2. Wählen Sie eine **[!UICONTROL Authenticated Profile Option]** (maximal 3). Dies sind die [geräteübergreifende Datenquellen](merge-rules-start.md) haben Sie zuvor erstellt.
3. Wählen Sie eine **[!UICONTROL Device Option]**. Zu den Optionen zählen:
   * **[!UICONTROL No Device Profile]**
   * **[!UICONTROL Current Device Profile]**
   * **[!UICONTROL Profile Link Device Graph]**
4. Klicken **[!UICONTROL Save]**.

### Überlegungen zu Adobe Campaign-Zielen, die geräteübergreifende IDs als Benutzer-ID-Schlüssel verwenden {#considerations}

Ende 2019 haben wir eine Reihe von Verbesserungen der Profilzusammenführungsrichtlinien veröffentlicht, um die Genauigkeit von Batch-Dateien zu verbessern, die mit geräteübergreifenden IDs generiert wurden. Diese Verbesserungen werden in Ihrer Audience Manager-Instanz ab Montag, dem 16. März 2020 strikt berücksichtigt. Folglich produzieren Segmente, die mit geräteübergreifenden IDs einem Ziel zugeordnet sind, in einigen Konfigurationen der Profilzusammenführungsrichtlinien keine Exporte mehr.

Um die korrekte Integration zwischen Ihrer Audience Manager-Instanz und Zielen mithilfe geräteübergreifender IDs wie Adobe Campaign sicherzustellen, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:

1. Überprüfen Sie die Profilzusammenführungsrichtlinie , die von den Segmenten verwendet wird, die Ihrem Adobe Campaign Declared ID-Ziel zugeordnet sind. Die Profilzusammenführungsrichtlinie muss die [!UICONTROL Last Authenticated Profile] -Option, sodass alle authentifizierten Profile in die Exporte einbezogen werden können. Wenn Ihre Profilzusammenführungsrichtlinie eine andere Option verwendet, wechseln Sie zu [!UICONTROL Last Authenticated Profile].
2. Wählen Sie die Datenquelle Adobe Campaign Declared ID in den Profilzusammenführungsregeleinstellungen aus.

>[!NOTE]
>
> Wenn Sie Ihre maximale Anzahl von [!UICONTROL Profile Merge Rules] und Sie bei der Konfiguration der Komponenten auf der Grundlage der oben stehenden Anweisungen Hilfe benötigen, wenden Sie sich an die Kundenunterstützung.

## Konfigurieren des Zusammenführungsregelcodes {#configure-merge-rule-code}

Befolgen Sie diese Anweisungen zum Einrichten der [!UICONTROL Adobe Experience Platform Identity Service], [!UICONTROL DIL], und mobile [!DNL SDK] -Code, um mit Ihren Zusammenführungsregeln zu arbeiten.

<!-- merge-rules-configure-code.xml -->

### Voraussetzungen

Sie müssen eine [geräteübergreifende Datenquelle](#create-data-source) und [Profilzusammenführungsregeln](#create-profile-merge-rule) *before* diese Verfahren abschließen.

## Für Adobe Experience Platform Identity Service-Kunden {#id-service-customers}

Die [!UICONTROL Adobe Experience Platform Identity Service] und die neueste Version von [DIL](../../dil/dil-overview.md) werden empfohlen, wenn Sie mit [!UICONTROL Profile Merge Rules]. Sie müssen jedoch nicht die [!UICONTROL Adobe Experience Platform Identity Service] , um mit dieser Funktion zu arbeiten. Wenn Sie nur [!UICONTROL DIL], siehe [Legacy-DIL-Abschnitt](#legacy-dil) unten.

### Konfigurieren der Funktion zum Festlegen der Kunden-ID

Beim Arbeiten mit [!UICONTROL Adobe Experience Platform Identity Service], die `setCustomerIDs` übergibt deklarierte IDs an [!DNL Audience Manager]. Um eine Profilzusammenführungsrichtlinie zu verwenden, müssen Sie `setCustomerIDs` , um den Integrationscode zu verwenden, der beim Erstellen einer geräteübergreifenden Datenquelle angegeben wurde. Angenommen, Sie haben eine geräteübergreifende Datenquelle mit dem Integrationscode erstellt. `my_datasource_ic`. Um eine deklarierte ID zu übergeben, fügen Sie den Integrationscode zur Besucher-ID-Funktion hinzu, wie im geänderten Code-Beispiel unten dargestellt.

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

Weitere Informationen finden Sie unter [Geräteübergreifende Datenquelle erstellen](#create-data-source) und [Kunden-IDs und Authentifizierungsstatus](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html).

### Konfigurieren `DIL.create` function

Die neuesten Versionen von [!UICONTROL DIL] nimmt nun automatisch die [!UICONTROL declared ID] von `visitorService` Funktion in `DIL.create` (siehe [Deklarierte ID-Variablen](../declared-ids.md#declared-id-variables)). Überprüfen Sie Ihre `DIL.create` -Funktion, um sicherzustellen, dass diese ordnungsgemäß eingerichtet ist, wie im Code-Beispiel unten dargestellt.

```js
var vDil = DIL.create({
   partner:"partner name",
   visitorService:{
      namespace:"INSERT-MCORG-ID-HERE"
   }
});
```

Im Schlüssel-Wert-Paar des Namespace muss die `*`MCORG`*` ist [!DNL Experience Cloud] Organisations-ID. Wenn Sie diese ID nicht haben, finden Sie sie im [!UICONTROL Administration] Abschnitt [!DNL Experience Cloud] Dashboard. Sie benötigen Administratorberechtigungen, um dieses Dashboard anzuzeigen. Siehe [Administration: Hauptdienste](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

### SDKs konfigurieren

Siehe [SDKs konfigurieren](#configure-sdks-legacy-dil) unten.

## Legacy-DIL {#legacy-dil}

Wenn Sie [!DNL Adobe Experience Platform Identity Service] Du solltest es wirklich tun. Wir wissen jedoch, dass die Umstellung auf neuen Code sorgfältiges Denken und Testen erfordert. In diesen Fällen überprüfen Sie Ihre `DIL.create` -Funktion, um sicherzustellen, dass diese ordnungsgemäß eingerichtet ist, wie im Code-Beispiel unten dargestellt.

```js
DIL.create({
   partner: "partner name",
   declaredId:{
      dpuuid: YOUR_DPUUID,
      dpid: YOUR_DPID
   }
});
```

Weitere Informationen finden Sie in der alten Version [!UICONTROL DIL] Abschnitt in [Deklarierte ID-Variablen](../declared-ids.md#declared-id-variables).

### SDKs konfigurieren {#configure-sdks-legacy-dil}

Überprüfen Sie die Methoden in Ihrem [!DNL SDK] Code, der die Übergabe ermöglicht [!UICONTROL declared IDs] von [!DNL Android] und [!DNL iOS] Mobilgeräte. Die Variablennamen für die [!DNL Android] und [!DNL iOS] -Codebibliotheken sind identisch:

* `dpid`: Die geräteübergreifende Datenquellen-ID.
* `dpuuid`: Die [!UICONTROL declared ID] (d. h. die Benutzer-ID).

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

Siehe auch [Audience Manager-Methoden für Android](https://experienceleague.adobe.com/docs/mobile-services/android/audience-manager-android/c-audience-manager-methods.html) und [Audience Manager-Methoden für iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/aam-methods.html).

>[!MORELIKETHIS]
>
>* [Erstellen einer Datenquelle](../manage-datasources.md#create-data-source)


---
description: Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an ein spezielles Amazon S3-Verzeichnis für Ihr Audience Manager-Konto senden. In diesem Abschnitt finden Sie Informationen zu Versand-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen.
seo-description: Send or update metadata files by sending them to a special Amazon S3 directory for your Audience Manager account. Refer to this section for information about delivery/directory paths, file processing times, and updates.
seo-title: Delivery Methods for Metadata Files
solution: Audience Manager
title: Bereitstellungsmethoden für Metadatendateien
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
feature: Log Files
exl-id: 6ef2a80c-2574-4446-b755-28027818b5eb
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---

# Bereitstellungsmethoden für Metadatendateien{#delivery-methods-for-metadata-files}

Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an ein spezielles [!DNL Amazon S3] für Ihr Audience Manager-Konto senden. In diesem Abschnitt finden Sie Informationen zu Versand-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen.

>[!IMPORTANT]
>
> Wenden Sie sich an Ihren Audience Manager-Berater oder an die Kundenunterstützung, um zu beginnen und ein [!DNL Amazon S3] für Ihre Metadatendateien einzurichten.

## Syntax und Beispiel eines Versandpfads {#syntax}

Die Daten werden für jeden Kunden in einem separaten Namespace in einem [!DNL Amazon S3] Verzeichnis gespeichert. Der Dateipfad folgt der unten gezeigten Syntax. Beachten Sie, dass spitze Klammern `<>` einen variablen Platzhalter angeben. Die anderen Elemente sind Konstanten und ändern sich nicht.

**Syntax:**

```
.../log_ingestion/pid=<AAM ID>/dpid=<d_src>/meta/<yyyymmdd_0_child ID>
```

**Beispiel:**

```
.../log_ingestion/pid=1121/dpid=3342/meta/20200112_0_4
```

<br>

In der folgenden Tabelle werden diese Elemente in einem Dateibereitstellungspfad definiert.


| Dateiparameter | Beschreibung |
|---------|----------|
| `.../log_ingestion/` | Dies ist der Beginn des Speicherpfads für das Verzeichnis. Sie erhalten den vollständigen Pfad, wenn alles eingerichtet ist. |
| `pid=<AAM ID>` | Dieses Schlüssel-Wert-Paar enthält Ihre Audience Manager-Kunden-ID. |
| `dpid=<d_src>` | Dieses Schlüssel-Wert-Paar enthält die Datenquellen-ID, die bei einem Ereignisaufruf übergeben wird. Die Datenquellen-ID ist der Wert, der alle Inhalte in Ihrer Datei mit den tatsächlichen Daten verknüpft, zu denen sie gehört. </br> Angenommen, Sie haben einen Kreativen mit der ID 123 und dem Namen „Advertiser Creative A“. Da ein Ereignisaufruf nur die ID übergibt, müssen Sie „Advertiser Creative A“ in die Metadatendatei aufnehmen. Die Kampagne und das Kreativ-Tool gehören zu einer Datenquelle. Durch die Datenquellen-ID werden diese miteinander verknüpft. So können wir Dateiinhalte genau mit einer ID verknüpfen, die bei einem Ereignisaufruf gesendet wird. Siehe [So bestimmen IDs von Ereignisaufrufen Dateinamen, Inhalte und Bereitstellungspfade](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-file-names). |
| `<yyyymmdd_0_child ID>` | Dies ist der Dateiname. Siehe [Benennungskonventionen für Metadatendateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Dateiverarbeitungszeiten und Aktualisierungen {#processing-times}

Metadatendateien werden viermal täglich in regelmäßigen Abständen verarbeitet.

Um Ihre Metadaten-Datensätze zu aktualisieren, senden Sie einfach eine Datei, die neue Informationen enthält. Sie müssen nicht jedes Mal vollständige Aktualisierungen senden.

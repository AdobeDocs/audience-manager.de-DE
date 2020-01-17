---
description: Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an einen speziellen Amazon S3-Ordner für Ihr Audience Manager-Konto senden. Informationen zu Bereitstellungs-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen finden Sie in diesem Abschnitt.
seo-description: Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an einen speziellen Amazon S3-Ordner für Ihr Audience Manager-Konto senden. Informationen zu Bereitstellungs-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen finden Sie in diesem Abschnitt.
seo-title: Bereitstellungsmethoden für Metadatendateien
solution: Audience Manager
title: Bereitstellungsmethoden für Metadatendateien
uuid: 5199ee9b-920d-423d-8070-05a017ecd562
translation-type: tm+mt
source-git-commit: de51f27cac0d165d043e90db978a6949d6a43761

---


# Bereitstellungsmethoden für Metadatendateien{#delivery-methods-for-metadata-files}

Senden oder aktualisieren Sie Metadatendateien, indem Sie sie an einen speziellen [!DNL Amazon S3] Ordner für Ihr Audience Manager-Konto senden. Informationen zu Bereitstellungs-/Ordnerpfaden, Dateiverarbeitungszeiten und Aktualisierungen finden Sie in diesem Abschnitt.

## Syntax und Beispiel des Bereitstellungspfads {#syntax}

Daten werden für jeden Kunden in einem [!DNL Amazon S3] Verzeichnis in einem separaten Namespace gespeichert. Der Dateipfad folgt der unten stehenden Syntax. Beachten Sie, dass spitze Klammern einen variablen Platzhalter `<>` angeben. Die anderen Elemente sind Konstanten und bleiben unverändert.

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
---------|----------|
| `.../log_ingestion/` | Dies ist der Anfang des Ordnerspeicherpfads. Sie erhalten den vollständigen Pfad, wenn alles eingerichtet ist. |
| `pid=<AAM ID>` | Dieses Schlüssel-Wert-Paar enthält Ihre Audience Manager-Kunden-ID. |
| `dpid=<d_src>` | Dieses Schlüssel-Wert-Paar enthält die Datenquelle-ID, die bei einem Ereignisaufruf weitergegeben wird. Die Datenquellen-ID ist der Wert, der den gesamten Inhalt Ihrer Datei mit den tatsächlichen Daten verknüpft, zu denen sie gehört. </br> Angenommen, Sie haben ein kreatives Element mit der ID 123 und dem Namen &quot;Werbetreibende Kreative A&quot;. Da ein Ereignisaufruf nur in der ID weitergegeben wird, müssen Sie &quot;Werbetreibende Kreative A&quot;in die Metadatendatei aufnehmen. Die Kampagne und das kreative Element gehören zu einer Datenquelle. Die Datenquellen-ID verbindet diese und ermöglicht es uns, Dateiinhalte exakt mit einer ID zu verknüpfen, die bei einem Ereignisaufruf gesendet wird. Siehe [Ermitteln von Dateinamen, Inhalten und Bereitstellungspfaden](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md#how-ids-shape-filenames)durch Ereignisaufruf-IDs. |
| `<yyyymmdd_0_child ID>` | Dies ist der Dateiname. Siehe [Benennungskonventionen für Metadatendateien](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). |

## Dateiverarbeitungszeiten und -aktualisierungen {#processing-times}

Metadaten-Dateien werden in regelmäßigen Abständen viermal am Tag verarbeitet.

Um Ihre Metadaten-Datensätze zu aktualisieren, senden Sie einfach eine Datei mit neuen Informationen. Sie müssen keine vollständigen Updates jedes Mal senden.

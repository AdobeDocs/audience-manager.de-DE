---
description: Formatieren Sie den Inhalt der Metadatendatei Ihrer Audience Optimization entsprechend diesen Spezifikationen.
seo-description: Formatieren Sie den Inhalt der Metadatendatei Ihrer Audience Optimization entsprechend diesen Spezifikationen.
seo-title: Inhaltsformat für Metadatendateien
solution: Audience Manager
title: Inhaltsformat für Metadatendateien
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: log files
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 5%

---


# Inhaltsformat für Metadatendateien{#content-format-for-metadata-files}

Formatieren Sie den Inhalt der Metadatendatei Ihrer Audience Optimization entsprechend diesen Spezifikationen.

## Syntax {#syntax}

Die folgende Syntax definiert die Struktur von gut geformten Inhalten in einer Metadatendatei. Hinweis: *kursiv* gibt einen Variablenplatzhalter an.

**Syntax:**  *content ID* |  *name* |  *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

Die dritte Spalte **-1** ist technisch die übergeordnete ID, bei der es sich um ein veraltetes Feld handelt. Der Wert sollte immer auf **-1** eingestellt werden.

>[!NOTE]
>
>Beachten Sie, dass pro Dimension eine Metadatendatei benötigt wird, sodass im Bucket mehrere Metadatendateien erwartet werden. Die Dimensionen werden im Artikel [Benennungsregeln für Metadatendatei](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension) aufgeführt.

**Separate Dateieinträge mit &quot;^a&quot;(Control-A&quot;oder &quot;ASCII 001&quot;)**

Verwenden Sie `^a` (control-A oder ASCII 001), um Inhalte in Ihren Metadatendateien zu trennen. Da es sich hierbei um nicht druckbare Zeichen handelt, zeigt das Syntaxbeispiel oben nur eine Pipe &quot;|&quot;für Anzeigezwecke.

Bei Bedarf können Sie die Beispieldatei [20181105_0_1](assets/20181105_0_1.zip) herunterladen. Entpacken Sie sie und bearbeiten Sie sie in Ihrem Editor Ihrer Wahl und passen Sie sie entsprechend Ihren tatsächlichen Metadateninhalt an, da sie bereits das erforderliche Trennzeichen enthält.

>[!IMPORTANT]
>
>Fügen Sie den Metadatendateien keine Kopfzeilen hinzu.

## Beispiele {#examples}

Schauen wir uns einmal an, wie Sie Inhalte in einer Metadatendatei strukturieren würden. Ein Teil dieser Struktur hängt von der Dimension ab. Die Dimensionen werden im Artikel [Benennungsregeln für Metadatendatei](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension) aufgeführt.

**Campaign**

In diesem Beispiel lautet der Dateiname 20180921_0_1 und die drei Spalten in der Datei: Kampagnen-ID, Name und übergeordnete ID.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Kreativ**

In diesem Beispiel lautet der Dateiname 20180827_0_2 und die drei Spalten in der Datei: Kreative ID, Name und übergeordnete ID.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Site**

In diesem Beispiel lautet der Dateiname 20180921_0_5 und die drei Spalten in der Datei: Site-ID, Name und übergeordnete ID.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```

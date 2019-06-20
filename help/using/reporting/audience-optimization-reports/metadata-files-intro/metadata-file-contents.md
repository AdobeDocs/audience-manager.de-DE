---
description: Formatieren Sie den Inhalt Ihrer Metadatendatei für Zielgruppenoptimierungen gemäß diesen Spezifikationen.
seo-description: Formatieren Sie den Inhalt Ihrer Metadatendatei für Zielgruppenoptimierungen gemäß diesen Spezifikationen.
seo-title: Inhaltsformat für Metadatendateien
solution: Audience Manager
title: Inhaltsformat für Metadatendateien
uuid: 9 ba 44738-3 e 17-40 c 7-9 e 8 c -5 abd 361 e 16 d
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Inhaltsformat für Metadatendateien{#content-format-for-metadata-files}

Formatieren Sie den Inhalt Ihrer Metadatendatei für Zielgruppenoptimierungen gemäß diesen Spezifikationen.

## Syntax {#syntax}

Die folgende Syntax definiert die Struktur gut formatierter Inhalte in einer Metadatendatei. Hinweis: *Kursiv* zeigt einen Variablenplatzhalter an.

**Syntax:***Inhalts-ID* | *name* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

Die dritte Spalte **-1** ist technisch gesehen die übergeordnete ID, die ein älteres Feld ist. Der Wert sollte immer als **-1 festgelegt** werden.

>[!NOTE]
>
>Beachten Sie, dass eine Metadatendatei pro Dimension benötigt wird, sodass mehrere Metadatendateien im Behälter erwartet werden. Die Dimensionen werden in den Artikelbenennungskonventionen [für Metadatendatei aufgeführt](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Separate Dateieinträge mit ^ a (Kontroll-A oder ASCII 001)**

Verwenden `^a` Sie (Kontroll-A oder ASCII 001), um Inhalte in Ihren Metadatendateien zu trennen. Da es sich hierbei um nicht druckbare Zeichen handelt, zeigt das obige Syntaxbeispiel ein Pipe-Symbol an. |&quot; nur anzuzeigen.

Bei Bedarf können Sie die Beispieldatei herunterladen [- 20181105_ 0_ 1](assets/20181105_0_1.zip). Dekomprimieren Sie die Datei und bearbeiten Sie sie im Editor Ihrer Wahl entsprechend Ihren tatsächlichen Metadateninhalten, da sie bereits das erforderliche Trennzeichen enthält.

>[!IMPORTANT]
>
>Fügen Sie Metadatendateien keine Kopfzeilen hinzu.

## Beispiele {#examples}

Sehen wir uns an, wie Sie den Inhalt in einer Metadatendatei strukturieren würden. Ein Teil dieser Struktur hängt von der Dimension ab. Die Dimensionen werden in den Artikelbenennungskonventionen [für Metadatendatei aufgeführt](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campaign**

In diesem Beispiel lautet der Dateititel 20180921_ 0_ 1 und die drei Spalten in der Datei sind: Kampagnen-ID, Name und übergeordnete ID.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Kreativ**

In diesem Beispiel lautet der Dateititel 20180827_ 0_ 2 und die drei Spalten in der Datei sind: Creative ID, Name und übergeordnete ID.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Site**

In diesem Beispiel lautet der Dateititel 20180921_ 0_ 5 und die drei Spalten in der Datei sind: Site-ID, Name und übergeordnete ID.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```

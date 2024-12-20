---
description: In diesem Artikel werden die Namenskonventionen beschrieben, die von der Schlüsselvariablen in einem Schlüssel-Wert-Paar verwendet werden.
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: Namensanforderungen für Schlüsselvariablen
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---

# Namensanforderungen für Schlüsselvariablen {#name-requirements-for-key-variables}

In diesem Artikel werden die Namenskonventionen beschrieben, die von der Schlüsselvariablen in einem Schlüssel-Wert-Paar verwendet werden.

## Benennungsanforderungen für Schlüssel

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder] kann der Name einer Schlüsselvariablen in einem Schlüssel-Wert-Paar aus einer beliebigen Anzahl von Ziffern bestehen, gefolgt von einem (oder mehreren) Buchstaben, einem Bindestrich, einem Unterstrich und zusätzlichen Ziffern.

* Gültige Schlüsselnamen: `price123`, `123price`, `price-123`, `c_price123`.

* Ungültige Schlüsselnamen: `123`, `price!123`.

## Präfix von Schlüsselvariablen mit `c_`

Das `c_`-Präfix ist *immer* erforderlich, wenn die Parameter, die Daten über eine Ereignisaufruf-URL senden, diese Syntax verwenden.

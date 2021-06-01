---
description: In diesem Artikel werden die Benennungskonventionen beschrieben, die von der Schlüsselvariablen in einem Schlüssel-Wert-Paar verwendet werden.
seo-description: In diesem Artikel werden die Benennungskonventionen beschrieben, die von der Schlüsselvariablen in einem Schlüssel-Wert-Paar verwendet werden.
seo-title: Anforderungen an Namen für Schlüsselvariablen
solution: Audience Manager
title: Anforderungen an Namen für Schlüsselvariablen
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: 'Eigenschaften '
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 12%

---

# Anforderungen an Namen für Schlüsselvariablen {#name-requirements-for-key-variables}

In diesem Artikel werden die Benennungskonventionen beschrieben, die von der Schlüsselvariablen in einem Schlüssel-Wert-Paar verwendet werden.

## Namensanforderungen für Schlüssel

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder] kann der Name einer Schlüsselvariablen in einem Schlüssel-Wert-Paar aus einer beliebigen Anzahl von Ziffern gefolgt von 1 (oder mehr) Buchstaben, einem Bindestrich, einem Unterstrich und zusätzlichen Ziffern bestehen.

* Gültige Schlüsselnamen: `price123`, `123price`, `price-123`, `c_price123`.

* Ungültige Schlüsselnamen: `123`, `price!123`.

## Präfix für Schlüsselvariablen mit `c_`

Das `c_`-Präfix ist *immer* erforderlich, wenn die Parameter, die Daten für eine Ereignisaufruf-URL senden, diese Syntax verwenden.

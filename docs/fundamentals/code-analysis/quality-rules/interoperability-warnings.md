---
title: Правила переносимости и взаимодействия (анализ кода)
description: Сведения о переносимости правил анализа кода и правилах взаимодействия
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- vs.codeanalysis.Portablityrules
- vs.codeanalysis.Interoperabilityrules
helpviewer_keywords:
- managed code analysis rules, interoperability rules, portability rules
- portability rules
- warnings, portability
- interoperability rules
- warnings, interoperability
author: gewarren
ms.author: gewarren
ms.openlocfilehash: a20cd77e13c4a8b95633d129990667f0a8de3ee8
ms.sourcegitcommit: 2e4adc490c1d2a705a0592b295d606b10b9f51f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592410"
---
# <a name="portability-and-interoperability-rules"></a>Правила переносимости и взаимодействия

Правила переносимости поддерживают переносимость на разных платформах. Правила взаимодействия поддерживают взаимодействие с клиентами COM.

## <a name="in-this-section"></a>В этом разделе

| Правило | Описание |
| - | - |
| [CA1401: методы P/Invoke не должны быть видимыми](ca1401.md) | Открытый или защищенный метод в открытом типе имеет атрибут System.Runtime.InteropServices.DllImportAttribute (также реализованное ключевым словом Declare в Visual Basic). Такие методы не следует делать видимыми. |
| [CA1416. Проверка совместимости платформ](ca1416.md) | Использование зависящих от платформы API-интерфейсов в компоненте делает код больше не работает на всех платформах. |
| [CA1417: не используйте `OutAttribute` в строковых параметрах для P/Invoke](ca1417.md) | Строковые параметры, передаваемые по значению, `OutAttribute` могут дестабилизировать среду выполнения, если строка является интернированной строкой. |

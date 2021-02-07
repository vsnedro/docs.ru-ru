---
description: 'Дополнительные сведения о методе: Вебхеадерколлектион. Аддинтернал'
title: Вебхеадерколлектион. Аддинтернал, метод (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.WebHeaderCollection.AddInternal
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 7bc84f84e6656dba5230b627fe9decfc4e0b4746
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699484"
---
# <a name="webheadercollectionaddinternal-method"></a>Вебхеадерколлектион. Аддинтернал, метод

Добавляет новый заголовок с указанным именем и значением в коллекцию, минуя проверки.

```csharp
internal void AddInternal(string name, string value)
```

> [!WARNING]
> Этот метод является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="parameters"></a>Параметры

- `name` <xref:System.String>

  Имя заголовка.

- `value` <xref:System.String>

  Значение заголовка.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System.dll)

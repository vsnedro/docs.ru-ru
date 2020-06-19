---
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
ms.openlocfilehash: fd7b13ccd1baad48ab99a85d80ccd6154651c608
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990463"
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

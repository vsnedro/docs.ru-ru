---
title: Класс Комнетос (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ComNetOS
- System.Net.ComNetOS.IsWin7orLater
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: ed2b970d07df2c338870b386e75c1688703f1d68
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990521"
---
# <a name="comnetos-class"></a>Класс Комнетос

Предоставляет сведения о текущей операционной системе, такие как версия и тип установки (клиент или сервер). Этот класс не может быть унаследован.
  
```csharp  
internal static class ComNetOS
```

> [!WARNING]
> Этот класс является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого класса в рабочем приложении при каких-либо обстоятельствах.

## <a name="iswin7orlater-field"></a>Поле IsWin7orLater

Указывает, является ли версия операционной системы Windows 7 или более поздней.

```csharp
internal static readonly bool IsWin7orLater
```

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.Net>

**Сборка:** Система (в System.dll)

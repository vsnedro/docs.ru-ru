---
description: 'Дополнительные сведения о: Комнетос Class'
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
ms.openlocfilehash: 7376fe4a5e02818907cb71573451fffb3a3667cb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802532"
---
# <a name="comnetos-class"></a>Класс ComNetOS

Предоставляет сведения о текущей операционной системе, такие как версия и тип установки (клиент или сервер). Этот класс не наследуется.
  
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

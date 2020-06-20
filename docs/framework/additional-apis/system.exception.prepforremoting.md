---
title: Метод Exception. Препфорремотинг (система)
description: Изучите метод Exception. Препфорремотинг в .NET. Метод добавляет в сообщение серверную трассировку стека, прежде чем исключение будет повторно создано на стороне клиента.
ms.date: 10/08/2019
topic_type:
- apiref
api_name:
- System.Exception.PrepForRemoting
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 9ceb73499ae3bb308975e6db5b961bfe40165ba3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105255"
---
# <a name="exceptionprepforremoting-method"></a>Метод Exception.PrepForRemoting

Сохраняет трассировку стека на стороне сервера, добавляя ее к сообщению, прежде чем исключение будет повторно создано на сайте вызова клиента.

```csharp
internal Exception PrepForRemoting();
```

## <a name="returns"></a>Возвращает

<xref:System.Exception>  
Данный экземпляр <xref:System.Exception>.

## <a name="remarks"></a>Remarks

> [!WARNING]
> `Exception.PrepForRemoting`Метод является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System>

**Сборка:** mscorlib.dll (в mscorlib.dll)

**.NET Framework версии:** Доступно с 1,0.

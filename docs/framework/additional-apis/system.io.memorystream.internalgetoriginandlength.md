---
description: Дополнительные сведения о методе MemoryStream. Интерналжеторигинандленгс
title: Метод MemoryStream. Интерналжеторигинандленгс (System.IO)
ms.date: 11/19/2019
topic_type:
- apiref
api_name:
- System.IO.MemoryStream.InternalGetOriginAndLength
api_location:
- mscorlib.dll
api_type:
- Assembly
ms.openlocfilehash: 4232852c0835a43454f36271a43062e1240297a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802545"
---
# <a name="memorystreaminternalgetoriginandlength-method"></a>Метод MemoryStream.InternalGetOriginAndLength

Возвращает внутренние значения источника и длину потока памяти.

```csharp
internal void InternalGetOriginAndLength(out int origin, out int length)
```

## <a name="parameters"></a>Параметры

- `origin` <xref:System.Int32>\
  При возврате из этого метода смещение массива байтов, указанного при создании нового <xref:System.IO.MemoryStream> объекта. Содержит 0, если массив байтов был создан <xref:System.IO.MemoryStream> .

- `length` <xref:System.Int32>\
  При возврате из этого метода число байтов в потоке памяти.

## <a name="remarks"></a>Remarks

> [!WARNING]
> `MemoryStream.InternalGetOriginAndLength`Метод является внутренним и не предназначен для непосредственного использования в коде.
>
> Корпорация Майкрософт не поддерживает использование этого метода в рабочем приложении при каких-либо обстоятельствах.

## <a name="requirements"></a>Требования

**Пространство имен:** <xref:System.IO>

**Сборка:** mscorlib.dll (в mscorlib.dll)

**Платформа .NET Framework версии:** Доступно с 2,0.

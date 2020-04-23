---
title: DacpGetModuleАдрес::Запрос Метод
ms.date: 01/16/2019
api.name:
- DacpGetModuleAddress::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- DacpGetModuleAddress::Request Method
helpviewer.keywords:
- DacpGetModuleAddress::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 4dbe6a2c295e5afae1b6761f0c7b695fdb906428
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102911"
---
# <a name="dacpgetmoduleaddressrequest-method"></a>DacpGetModuleАдрес::Запрос Метод

Выполняет запрос на заселяют структуру из заданной структуры времени выполнения.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Request(
    [in] IXCLRDataModule* pDataModule
);
```

## <a name="parameters"></a>Параметры

`pDataModule`\
(в) Указатель на модуль данных семян.

## <a name="remarks"></a>Remarks

Эта структура живет в времени выполнения и не подвергается воздействию каких-либо заголовков или файлов библиотек. Проще всего имитировать реализацию:

- Возврат значения, полученного `Request` от вызова `IXCLRDataModule*` метода по параметру со следующими параметрами:`((uint32) 0xf0000000, 0, 0, (uint32) sizeof(*this), (uint8*) this)`

## <a name="requirements"></a>Требования

**Платформы:** Посмотреть [системные требования](../../../../docs/framework/get-started/system-requirements.md)\
**Заголовок:** Нет
**Библиотека:** Нет
**Рамочные версии .NET:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>См. также раздел

- [Отладка](index.md)
- [DacpGetModuleАдрес структуры](dacpgetmoduleaddress-structure.md)

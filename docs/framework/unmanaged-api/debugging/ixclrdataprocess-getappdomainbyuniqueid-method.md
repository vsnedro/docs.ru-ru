---
description: 'Дополнительные сведения о методе: Иксклрдатапроцесс:: Жетаппдомаинбюникуеид'
title: 'Метод Иксклрдатапроцесс:: Жетаппдомаинбюникуеид'
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method
helpviewer.keywords:
- IXCLRDataProcess::GetAppDomainByUniqueId Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 7087362efbb810fcb6e1b6f7eb9f23c54c38fade
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800673"
---
# <a name="ixclrdataprocessgetappdomainbyuniqueid-method"></a>Метод Иксклрдатапроцесс:: Жетаппдомаинбюникуеид

Получает `AppDomain` в процессе на основе его уникального идентификатора.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT GetAppDomainByUniqueID(
    [in] ULONG64               id,
    [out] IXCLRDataAppDomain **appDomain
);
```

## <a name="parameters"></a>Параметры

`id`\
окне Уникальный идентификатор домена приложения

`appDomain`\
заполняет AppDomain

## <a name="remarks"></a>Remarks

Предоставленный метод является частью `IXCLRDataProcess` интерфейса и соответствует слоту 20 таблицы виртуальных методов. `IXCLRDataAppDomain*`Возвращаемый объект используется для взаимодействия с другими API.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).
**Заголовок:** Нет **библиотеки:** нет **платформа .NET Framework версий:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]

## <a name="see-also"></a>См. также

- [Отладка](index.md)
- [Интерфейс IXCLRDataProcess](ixclrdataprocess-interface.md)

---
description: 'Дополнительные сведения о методе: ICorDebugManagedCallback:: break'
title: Метод ICorDebugManagedCallback::Break
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Break
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Break
helpviewer_keywords:
- Break method [.NET Framework debugging]
- ICorDebugManagedCallback::Break method [.NET Framework debugging]
ms.assetid: 7d78a301-82b3-43b2-9d65-3cda3285ae97
topic_type:
- apiref
ms.openlocfilehash: 2ef273a693291685c4c3a0ce2b20ed45613e3376
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801219"
---
# <a name="icordebugmanagedcallbackbreak-method"></a>Метод ICorDebugManagedCallback::Break

Уведомляет отладчик о <xref:System.Reflection.Emit.OpCodes.Break> выполнении инструкции в потоке кода.

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Break (
    [in] ICorDebugAppDomain *pAppDomain,
    [in] ICorDebugThread    *thread
);
```

## <a name="parameters"></a>Параметры

`pAppDomain`\
окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащий инструкцию Break.

`thread`\
окне Указатель на объект ICorDebugThread, представляющий поток, содержащий инструкцию Break.

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)

---
description: 'Дополнительные сведения о методе: ICorDebugController:: Continue'
title: Метод ICorDebugController::Continue
ms.date: 03/30/2017
api_name:
- ICorDebugController.Continue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::Continue
helpviewer_keywords:
- Continue method [.NET Framework debugging]
- ICorDebugController::Continue method [.NET Framework debugging]
ms.assetid: 8684cd06-ad3e-48ef-832e-15320e1f43a2
topic_type:
- apiref
ms.openlocfilehash: e5858a8c287e8dd5a493a85c9f427ad8acd9ecc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710807"
---
# <a name="icordebugcontrollercontinue-method"></a>Метод ICorDebugController::Continue

Возобновляет выполнение управляемых потоков после вызова [метода остановкой](icordebugcontroller-stop-method.md).

## <a name="syntax"></a>Синтаксис

```cpp
HRESULT Continue (
    [in] BOOL fIsOutOfBand
);
```

## <a name="parameters"></a>Параметры

`fIsOutOfBand`  
окне Задайте значение `true` , если продолжение события вне диапазона. в противном случае задайте для значение `false` .

## <a name="remarks"></a>Remarks

`Continue` продолжит процесс после вызова `ICorDebugController::Stop` метода.

При отладке в смешанном режиме не вызывайте метод `Continue` в потоке событий Win32, если вы не продолжите работу по внешнему событию.

*Событие с чередованием* — это управляемое событие или нормальное неуправляемое событие, в течение которого отладчик поддерживает взаимодействие с управляемым состоянием процесса. В этом случае отладчик получает обратный вызов [икордебугунманажедкаллбакк::D ебужевент](icordebugunmanagedcallback-debugevent-method.md) с `fOutOfBand` параметром, имеющим значение `false` .

*Событие внешнего вида* — это неуправляемое событие, в течение которого взаимодействие с управляемым состоянием процесса невозможно, пока процесс остановлен из-за события. В этом случае отладчик получает `ICorDebugUnmanagedCallback::DebugEvent` обратный вызов с `fOutOfBand` параметром, для которого задано значение `true` .

## <a name="requirements"></a>Требования

**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).

**Заголовок:** CorDebug.idl, CorDebug.h

**Библиотека:** CorGuids.lib

**Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

---
description: 'Дополнительные сведения о методе: ICorDebugProcess:: getHandler'
title: Метод ICorDebugProcess::GetHandle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type:
- apiref
ms.openlocfilehash: fbc92be53b30d3c70f85fea36e05c6a5514b0f03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722130"
---
# <a name="icordebugprocessgethandle-method"></a>Метод ICorDebugProcess::GetHandle

Возвращает маркер процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
## <a name="parameters"></a>Параметры  

 `phProcessHandle`  
 заполняет Указатель на `HPROCESS` , который является обработчиком для процесса.  
  
## <a name="remarks"></a>Remarks  

 Полученный обработчик принадлежит интерфейсу отладки. Отладчик должен дублировать этот обработчик перед его использованием.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

---
description: 'Дополнительные сведения о методе: ICorDebugProcess:: EnumerateAppDomains'
title: Метод ICorDebugProcess::EnumerateAppDomains
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.EnumerateAppDomains
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::EnumerateAppDomains
helpviewer_keywords:
- ICorDebugProcess::EnumerateAppDomains method [.NET Framework debugging]
- EnumerateAppDomains method [.NET Framework debugging]
ms.assetid: d508981f-e2b2-445b-a649-69951c22702d
topic_type:
- apiref
ms.openlocfilehash: d212fafe7ae1355ba69e07b88c3b96119371fe43
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691527"
---
# <a name="icordebugprocessenumerateappdomains-method"></a>Метод ICorDebugProcess::EnumerateAppDomains

Перечисляет все домены приложений в этом процессе.  
  
## <a name="syntax"></a>Синтаксис  
  
``` cpp
HRESULT EnumerateAppDomains(  
    [out] ICorDebugAppDomainEnum **ppAppDomains);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppAppDomains`  
 заполняет Указатель на адрес [икордебугаппдомаиненум](icordebugappdomainenum-interface.md) , который является перечислителем для доменов приложений в этом процессе.  
  
## <a name="remarks"></a>Remarks  

 Этот метод можно использовать перед обратным вызовом [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

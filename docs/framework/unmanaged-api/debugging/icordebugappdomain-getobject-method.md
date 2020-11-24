---
title: Метод ICorDebugAppDomain::GetObject
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.GetObject
api_location:
- corguids.lib
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::GetObject
helpviewer_keywords:
- ICorDebugAppDomain::GetObject method [.NET Framework debugging]
- GetObject method, ICorDebugAppDomain interface [.NET Framework debugging]
ms.assetid: 78232e6f-ae18-4cfa-a6cd-e79471cf9d76
topic_type:
- apiref
ms.openlocfilehash: a163667ea7eca1ed817d642efdb8fc4efa2a0651
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95676066"
---
# <a name="icordebugappdomaingetobject-method"></a>Метод ICorDebugAppDomain::GetObject

Возвращает указатель интерфейса на домен приложения среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetObject (  
    [out] ICorDebugValue   **ppObject  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppObject`  
 заполняет Указатель на адрес объекта интерфейса ICorDebugValue, который представляет домен приложения среды CLR.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Если управляемый <xref:System.AppDomain?displayProperty=nameWithType> объект не был создан для этого домена приложения, метод возвращает `S_FALSE` и помещает `NULL` в `*ppObject` .  
  
## <a name="remarks"></a>Комментарии  

 Каждый домен приложения в процессе может иметь управляемый <xref:System.AppDomain?displayProperty=nameWithType> объект в среде выполнения, который представляет его. Эта функция получает объект интерфейса ICorDebugValue, соответствующий этому управляемому <xref:System.AppDomain?displayProperty=nameWithType> объекту.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]

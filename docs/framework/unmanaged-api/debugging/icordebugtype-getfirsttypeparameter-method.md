---
title: Метод ICorDebugType::GetFirstTypeParameter
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetFirstTypeParameter
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetFirstTypeParameter
helpviewer_keywords:
- ICorDebugType::GetFirstTypeParameter method [.NET Framework debugging]
- GetFirstTypeParameter method [.NET Framework debugging]
ms.assetid: 35bb594f-af6a-4349-83fe-e98702674e03
topic_type:
- apiref
ms.openlocfilehash: be69636056d5510b72dbce39917f5e8d3b05cd87
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723978"
---
# <a name="icordebugtypegetfirsttypeparameter-method"></a>Метод ICorDebugType::GetFirstTypeParameter

Возвращает указатель интерфейса на объект ICorDebugType, представляющий первый <xref:System.Type> параметр типа, представленного этим объектом `ICorDebugType` .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFirstTypeParameter (  
    [out] ICorDebugType   **value  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `value`  
 заполняет Указатель на адрес `ICorDebugType` объекта, представляющий первый параметр.  
  
## <a name="remarks"></a>Комментарии  

 `GetFirstTypeParameter` может вызываться в случаях, когда дополнительные сведения о типе в большинстве случаев входят в один параметр типа. В частности, его можно использовать, если тип является ELEMENT_TYPE_ARRAY, ELEMENT_TYPE_SZARRAY, ELEMENT_TYPE_BYREF или ELEMENT_TYPE_PTR, как показано в методе [ICorDebugType:: GetType](icordebugtype-gettype-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

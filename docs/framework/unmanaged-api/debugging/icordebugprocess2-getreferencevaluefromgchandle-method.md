---
title: Метод ICorDebugProcess2::GetReferenceValueFromGCHandle
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.GetReferenceValueFromGCHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::GetReferenceValueFromGCHandle
helpviewer_keywords:
- GetReferenceValueFromGCHandle method [.NET Framework debugging]
- ICorDebugProcess2::GetReferenceValueFromGCHandle method [.NET Framework debugging]
ms.assetid: 8bdd7f4c-19f2-4ede-875e-603773e8c128
topic_type:
- apiref
ms.openlocfilehash: a5b9d57aab834ba3ca72a2ea8576ec70cd88eb77
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713578"
---
# <a name="icordebugprocess2getreferencevaluefromgchandle-method"></a>Метод ICorDebugProcess2::GetReferenceValueFromGCHandle

Возвращает указатель ссылки на указанный управляемый объект, который имеет обработчик сборки мусора.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetReferenceValueFromGCHandle (  
    [in]  UINT_PTR                 handle,  
    [out] ICorDebugReferenceValue  **pOutValue  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `handle`  
 окне Указатель на управляемый объект, который имеет обработчик сборки мусора. Это значение является <xref:System.IntPtr> объектом и может быть получено из объекта <xref:System.Runtime.InteropServices.GCHandle> для управляемого объекта.  
  
 `pOutValue`  
 заполняет Указатель на адрес объекта ICorDebugReferenceValue, который представляет ссылку на указанный управляемый объект.  
  
## <a name="remarks"></a>Комментарии  

 Не путайте возвращаемое ссылочное значение со ссылочным значением сборки мусора.  
  
 Возвращаемая ссылка ведет себя как обычная ссылка. Он отключен, когда выполнение кода продолжится после точки останова. Время существования целевого объекта не зависит от времени существования ссылочного значения.  
  
> [!NOTE]
> `GetReferenceValueFromGCHandle`Метод не проверяет этот обработчик. Таким образом, `GetReferenceValueFromGCHandle` метод может привести к повреждению отладчика и отлаживаемого кода при передаче недопустимого маркера.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

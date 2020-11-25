---
title: Метод ICorDebugHeapValue2::CreateHandle
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
ms.openlocfilehash: 278120c6e1bc87a061a3f81f71bdb7b89cd421be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726565"
---
# <a name="icordebugheapvalue2createhandle-method"></a>Метод ICorDebugHeapValue2::CreateHandle

Создает маркер указанного типа для значения кучи, представленного этим объектом ICorDebugHeapValue2.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `type`  
 окне Значение перечисления Кордебугхандлетипе, указывающее тип создаваемого обработчика.  
  
 `ppHandle`  
 заполняет Указатель на адрес объекта ICorDebugHandleValue, который представляет новый маркер для этого значения кучи.  
  
## <a name="remarks"></a>Комментарии  

 Этот маркер будет создан в домене приложения, связанном со значением кучи, и станет недействительным при выгрузке домена приложения.  
  
 Несколько вызовов этой функции для одного значения кучи будут создавать несколько дескрипторов. Поскольку дескрипторы влияют на производительность сборщика мусора, отладчик должен ограничиваться относительно небольшим количеством дескрипторов (около 256), которые активны за один раз.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

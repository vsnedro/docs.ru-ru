---
description: 'Дополнительные сведения о методе: ICorDebugHeapValue2:: CreateHandle'
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
ms.openlocfilehash: d93fee71441b9c510d517acb9582b8d1d9ce9e10
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803663"
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
  
## <a name="remarks"></a>Remarks  

 Этот маркер будет создан в домене приложения, связанном со значением кучи, и станет недействительным при выгрузке домена приложения.  
  
 Несколько вызовов этой функции для одного значения кучи будут создавать несколько дескрипторов. Поскольку дескрипторы влияют на производительность сборщика мусора, отладчик должен ограничиваться относительно небольшим количеством дескрипторов (около 256), которые активны за один раз.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

---
description: 'Дополнительные сведения о методе: ICorDebugVariableHome:: Жетлокатионтипе'
title: 'Метод ICorDebugVariableHome:: Жетлокатионтипе'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLocationType
helpviewer_keywords:
- ICorDebugVariableHome::GetLocationType method [.NET Framework debugging]
- GetLocationType method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: 88027c55-8ec6-4f1e-a55b-7eefdbbc3515
topic_type:
- apiref
ms.openlocfilehash: 6efe9c045641d162be820961ca75c21a2b8fc14b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728799"
---
# <a name="icordebugvariablehomegetlocationtype-method"></a>Метод ICorDebugVariableHome:: Жетлокатионтипе

Возвращает тип собственного расположения переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetLocationType(  
    [out] VariableLocationType *pLocationType  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pLocationType`  
 заполняет Указатель на тип собственного расположения переменной.  Дополнительные сведения см. в описании перечисления [вариаблелокатионтипе](variablelocationtype-enumeration.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugVariableHome](icordebugvariablehome-interface.md)
- [Перечисление VariableLocationType](variablelocationtype-enumeration.md)

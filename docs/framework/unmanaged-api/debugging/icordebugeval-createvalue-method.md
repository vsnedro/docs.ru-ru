---
title: Метод ICorDebugEval::CreateValue
ms.date: 03/30/2017
api_name:
- ICorDebugEval.CreateValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::CreateValue
helpviewer_keywords:
- ICorDebugEval::CreateValue method [.NET Framework debugging]
- CreateValue method [.NET Framework debugging]
ms.assetid: 9a1c0b47-6f10-4fcb-844a-4ab2d7990140
topic_type:
- apiref
ms.openlocfilehash: 55888786fdd8ff2b1d5610a74ee729db0d4fcfde
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976256"
---
# <a name="icordebugevalcreatevalue-method"></a>Метод ICorDebugEval::CreateValue
Создает значение указанного типа с начальным значением нуль или null.  
  
 Этот метод является устаревшим в .NET Framework версии 2,0. Вместо этого используйте [ICorDebugEval2:: креатевалуефортипе](icordebugeval2-createvaluefortype-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateValue (  
    [in] CorElementType     elementType,  
    [in] ICorDebugClass     *pElementClass,  
    [out] ICorDebugValue    **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `elementType`  
 окне Значение перечисления [корелементтипе](../metadata/corelementtype-enumeration.md) , указывающее тип значения.  
  
 `pElementClass`  
 окне Указатель на объект [ICorDebugClass](icordebugclass-interface.md) , указывающий класс значения, если тип не является типом-примитивом.  
  
 `ppValue`  
 заполняет Указатель на адрес объекта "ICorDebugValue", представляющего значение.  
  
## <a name="remarks"></a>Remarks  
 `CreateValue`создает `ICorDebugValue` объект данного типа для единственной цели использования в вычислении функции. Этот объект значения можно использовать для передачи пользовательских констант в качестве параметров.  
  
 Если тип значения является типом-примитивом, его начальное значение равно нулю или null. Используйте [ICorDebugGenericValue:: SetValue](icordebuggenericvalue-setvalue-method.md) , чтобы задать значение типа-примитива.  
  
 Если значение `elementType` равно ELEMENT_TYPE_CLASS, вы получаете "ICorDebugReferenceValue" (возвращаемый в `ppValue`), представляющий ссылку на пустой объект. Этот объект можно использовать для передачи значения NULL в вычисление функции, имеющей параметры ссылки на объект. Нельзя задать значение, `ICorDebugValue` равное чему; Он всегда остается пустым.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 1,1, 1,0  
  
## <a name="see-also"></a>См. также раздел

- [Метод CreateValueForType](icordebugeval2-createvaluefortype-method.md)
- [Интерфейс ICorDebugEval](icordebugeval-interface.md)

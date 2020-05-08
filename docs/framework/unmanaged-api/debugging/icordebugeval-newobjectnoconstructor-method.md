---
title: Метод ICorDebugEval::NewObjectNoConstructor
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObjectNoConstructor
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObjectNoConstructor
helpviewer_keywords:
- NewObjectNoConstructor method [.NET Framework debugging]
- ICorDebugEval::NewObjectNoConstructor method [.NET Framework debugging]
ms.assetid: 80d509ca-b5e3-4c46-9c14-800db73d9bf7
topic_type:
- apiref
ms.openlocfilehash: d41216eb7da57d29d67ce17372f746328204649e
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976178"
---
# <a name="icordebugevalnewobjectnoconstructor-method"></a>Метод ICorDebugEval::NewObjectNoConstructor
Выделяет новый экземпляр объекта указанного типа без попытки вызова метода конструктора.  
  
 Этот метод является устаревшим в .NET Framework версии 2,0. Вместо этого используйте [ICorDebugEval2:: невпараметеризедобжектноконструктор](icordebugeval2-newparameterizedobjectnoconstructor-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NewObjectNoConstructor (  
    [in] ICorDebugClass     *pClass  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pClass`  
 окне Указатель на объект ICorDebugClass, представляющий тип объекта, для которого создается экземпляр.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:** 1,1, 1,0  
  
## <a name="see-also"></a>См. также раздел

- [Метод NewParameterizedObjectNoConstructor](icordebugeval2-newparameterizedobjectnoconstructor-method.md)

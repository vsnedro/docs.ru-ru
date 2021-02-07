---
description: 'Дополнительные сведения о методе: ICorDebugEval:: NewObject'
title: Метод ICorDebugEval::NewObject
ms.date: 03/30/2017
api_name:
- ICorDebugEval.NewObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::NewObject
helpviewer_keywords:
- NewObject method [.NET Framework debugging]
- ICorDebugEval::NewObject method [.NET Framework debugging]
ms.assetid: ce3025e8-defa-4c5e-8298-f49d71fa5736
topic_type:
- apiref
ms.openlocfilehash: 0f7feb53d061e5dbc453015772b97f2a5a59bbb3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693958"
---
# <a name="icordebugevalnewobject-method"></a>Метод ICorDebugEval::NewObject

Выделяет новый экземпляр объекта и вызывает указанный метод конструктора.  
  
 Этот метод является устаревшим в платформа .NET Framework версии 2,0. Вместо этого используйте [ICorDebugEval2:: невпараметеризедобжект](icordebugeval2-newparameterizedobject-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NewObject (  
    [in] ICorDebugFunction  *pConstructor,  
    [in] ULONG32            nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pConstructor`  
 окне Вызываемый конструктор.  
  
 `nArgs`  
 [in] Размер массива `ppArgs`.  
  
 `ppArgs`  
 окне Массив объектов ICorDebugValue, каждый из которых представляет аргумент, передаваемый конструктору.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:** 1,1, 1,0  
  
## <a name="see-also"></a>См. также

- [Метод NewParameterizedObject](icordebugeval2-newparameterizedobject-method.md)

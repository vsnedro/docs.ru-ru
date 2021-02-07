---
description: 'Дополнительные сведения о методе: ICorDebugEval2:: Невпараметеризедобжект'
title: Метод ICorDebugEval2::NewParameterizedObject
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type:
- apiref
ms.openlocfilehash: 2dc746fdada0e79044a1387bd4cb1c11b81d7777
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99693685"
---
# <a name="icordebugeval2newparameterizedobject-method"></a>Метод ICorDebugEval2::NewParameterizedObject

Создает новый объект параметризованного типа и вызывает метод конструктора объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pConstructor`  
 окне Указатель на объект ICorDebugFunction, представляющий конструктор объекта, для которого создается экземпляр.  
  
 `nTypeArgs`  
 окне Число переданных аргументов типа.  
  
 `ppTypeArgs`  
 окне Массив указателей, каждый из которых указывает на объект ICorDebugType, представляющий аргумент типа для объекта, для которого создается экземпляр.  
  
 `nArgs`  
 окне Число аргументов, переданных конструктору.  
  
 `ppArgs`  
 окне Массив указателей, каждый из которых указывает на объект ICorDebugValue, представляющий значение аргумента, передаваемое конструктору.  
  
## <a name="remarks"></a>Remarks  

 Конструктор объекта может принимать <xref:System.Type> Параметры.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

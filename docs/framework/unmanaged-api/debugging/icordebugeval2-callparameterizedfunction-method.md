---
title: Метод ICorDebugEval2::CallParameterizedFunction
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.CallParameterizedFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::CallParameterizedFunction
helpviewer_keywords:
- ICorDebugEval2::CallParameterizedFunction method [.NET Framework debugging]
- CallParameterizedFunction method [.NET Framework debugging]
ms.assetid: 72f54a45-dbe6-4bb4-8c99-e879a27368e5
topic_type:
- apiref
ms.openlocfilehash: 72bcc2479f7b6f41b384fc2517f0b04694663398
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976152"
---
# <a name="icordebugeval2callparameterizedfunction-method"></a>Метод ICorDebugEval2::CallParameterizedFunction
Настраивает вызов указанного ICorDebugFunction, который может быть вложен в класс, конструктор которого принимает <xref:System.Type> параметры или сам может принимать <xref:System.Type> параметры.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CallParameterizedFunction (  
    [in] ICorDebugFunction     *pFunction,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pFunction`  
 окне Указатель на `ICorDebugFunction` объект, представляющий вызываемую функцию.  
  
 `nTypeArgs`  
 окне Число аргументов, которые принимает функция.  
  
 `ppTypeArgs`  
 окне Массив указателей, каждый из которых указывает на объект ICorDebugType, представляющий аргумент функции.  
  
 `nArgs`  
 окне Количество значений, переданных функции.  
  
 `ppArgs`  
 окне Массив указателей, каждый из которых указывает на объект ICorDebugValue, представляющий значение, передаваемое в аргументе функции.  
  
## <a name="remarks"></a>Remarks  
 `CallParameterizedFunction`имеет вид [ICorDebugEval:: CallFunction](icordebugeval-callfunction-method.md) , за исключением того, что функция может находиться внутри класса с параметрами типа, может иметь параметры типа или и то, и другое. Аргументы типа должны быть даны сначала для класса, а затем для функции.  
  
 Если функция находится в другом домене приложения, произойдет переход. Однако все аргументы типа и значения должны находиться в целевом домене приложения.  
  
 Вычисление функций может выполняться только в ограниченных сценариях. Если `CallParameterizedFunction` или `ICorDebugEval::CallFunction` завершается ошибкой, возвращаемое значение HRESULT будет указывать на наиболее общую возможную причину сбоя.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

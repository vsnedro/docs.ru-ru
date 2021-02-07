---
description: 'Дополнительные сведения: метод ICorDebugFunction:: Жетнативекоде'
title: Метод ICorDebugFunction::GetNativeCode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
ms.openlocfilehash: 8938e11a5fdc3aa693faf04eec639941475d95ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99692450"
---
# <a name="icordebugfunctiongetnativecode-method"></a>Метод ICorDebugFunction::GetNativeCode

Возвращает машинный код для функции, представленной этим экземпляром ICorDebugFunction.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppCode`  
 заполняет Указатель на экземпляр ICorDebugCode, представляющий машинный код для этой функции, или значение null, если эта функция является кодом MSIL, который не был скомпилирован JIT-КОМПИЛЯТОРом.  
  
## <a name="remarks"></a>Remarks  

 Если функция, представленная этим `ICorDebugFunction` экземпляром, скомпилирована JIT-компилятором более одного раза, как в случае универсальных типов, `GetNativeCode` возвращает произвольный объект машинного кода.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

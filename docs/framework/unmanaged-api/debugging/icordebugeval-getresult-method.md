---
title: Метод ICorDebugEval::GetResult
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
ms.openlocfilehash: 86c017f581c7b980b8b0cb8bd7bdc1b0aa439afe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705830"
---
# <a name="icordebugevalgetresult-method"></a>Метод ICorDebugEval::GetResult

Возвращает результаты этой оценки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppResult`  
 заполняет Указатель на адрес объекта ICorDebugValue, который представляет результаты этой оценки, если вычисление завершается нормально.  
  
## <a name="remarks"></a>Комментарии  

 `GetResult`Метод действителен только после завершения оценки.  
  
 Если вычисление завершается обычным образом, `ppResult` задает результаты. Если оно завершается с исключением, результатом является исключение. Если вычисление выполнялось для нового объекта, результатом является ссылка на новый объект.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

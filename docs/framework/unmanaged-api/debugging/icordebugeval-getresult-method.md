---
description: 'Дополнительные сведения о методе: ICorDebugEval:: with Result'
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
ms.openlocfilehash: 03ab00f5c9a538e11a2046da9cbfd5ad7225231c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99694244"
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
  
## <a name="remarks"></a>Remarks  

 `GetResult`Метод действителен только после завершения оценки.  
  
 Если вычисление завершается обычным образом, `ppResult` задает результаты. Если оно завершается с исключением, результатом является исключение. Если вычисление выполнялось для нового объекта, результатом является ссылка на новый объект.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

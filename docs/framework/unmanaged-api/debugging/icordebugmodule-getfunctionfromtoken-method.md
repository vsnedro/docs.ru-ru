---
description: 'Дополнительные сведения о методе: ICorDebugModule:: Жетфунктионфромтокен'
title: Метод ICorDebugModule::GetFunctionFromToken
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetFunctionFromToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetFunctionFromToken
helpviewer_keywords:
- GetFunctionFromToken method, ICorDebugModule interface [.NET Framework debugging]
- ICorDebugModule::GetFunctionFromToken method [.NET Framework debugging]
ms.assetid: 6fe12194-4ef7-43c1-9570-ade35ccf127a
topic_type:
- apiref
ms.openlocfilehash: d6da43441f3774cff44a6f867c3ccf2a8581ebab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691657"
---
# <a name="icordebugmodulegetfunctionfromtoken-method"></a>Метод ICorDebugModule::GetFunctionFromToken

Возвращает функцию, заданную маркером метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFunctionFromToken(  
    [in] mdMethodDef methodDef,  
    [out] ICorDebugFunction **ppFunction  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `methodDef`  
 окне `mdMethodDef` Токен метаданных, который ссылается на метаданные функции.  
  
 `ppFunction`  
 заполняет Указатель на адрес объекта интерфейса ICorDebugFunction, представляющего функцию.  
  
## <a name="remarks"></a>Remarks  

 `GetFunctionFromToken`Метод возвращает CORDBG_E_FUNCTION_NOT_IL HRESULT, если переданное значение `methodDef` не ссылается на метод языка MSIL.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

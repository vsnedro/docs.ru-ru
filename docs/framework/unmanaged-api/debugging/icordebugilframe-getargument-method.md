---
description: 'Дополнительные сведения о методе: ICorDebugILFrame:: Argument'
title: Метод ICorDebugILFrame::GetArgument
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
ms.openlocfilehash: c845f3c07502f3b1ce564833ee6ef98e3305463f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650512"
---
# <a name="icordebugilframegetargument-method"></a>Метод ICorDebugILFrame::GetArgument

Возвращает значение указанного аргумента в кадре стека MSIL.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwIndex`  
 окне Индекс аргумента в этом кадре стека MSIL.  
  
 `ppValue`  
 [из] Указатель на адрес объекта ICorDebugValue, представляющего извлеченное значение.  
  
## <a name="remarks"></a>Remarks  

 `GetArgument`Метод можно использовать либо в кадре стека MSIL, либо в кадре JIT-компиляции.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

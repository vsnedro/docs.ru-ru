---
description: 'Дополнительные сведения о методе: ICorDebugThread2:: GetActiveFunctions'
title: Метод ICorDebugThread2::GetActiveFunctions
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.GetActiveFunctions
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::GetActiveFunctions
helpviewer_keywords:
- GetActiveFunctions method [.NET Framework debugging]
- ICorDebugThread2::GetActiveFunctions method [.NET Framework debugging]
ms.assetid: 27fae01a-ecec-423a-973e-24f8de55826c
topic_type:
- apiref
ms.openlocfilehash: 841e8ff17f15cfb14e1c1bf65c651a5177db2eaa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658767"
---
# <a name="icordebugthread2getactivefunctions-method"></a>Метод ICorDebugThread2::GetActiveFunctions

Возвращает сведения об активной функции в каждом кадре этого потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetActiveFunctions (  
    [in]   ULONG32             cFunctions,  
    [out]  ULONG32             *pcFunctions,  
    [in, out, size_is(cFunctions), length_is(*pcFunctions)]  
        COR_ACTIVE_FUNCTION    pFunctions[]  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `cFunctions`  
 [in] Размер массива `pFunctions`.  
  
 `pcFunctions`  
 заполняет Указатель на число объектов, возвращаемых в `pFunctions` массиве. Число возвращаемых объектов будет равно числу управляемых кадров в стеке.  
  
 `pFunctions`  
 [вход, выход] Массив объектов COR_ACTIVE_FUNCTION, каждый из которых содержит сведения об активных функциях в кадрах этого потока.  
  
 Первый элемент будет использоваться для конечного фрейма и так далее — в корне стека.  
  
## <a name="remarks"></a>Remarks  

 Если `pFunctions` для входных данных задано значение null, `GetActiveFunctions` функция возвращает только число функций в стеке. То есть если `pFunctions` во входных данных параметр имеет значение null, `GetActiveFunctions` возвращает значение только в `pcFunctions` .  
  
 `GetActiveFunctions`Метод предназначен для оптимизации при получении тех же сведений из кадров в трассировке стека и включает только те кадры, для которых в полной трассировке стека был бы объект ICorDebugILFrame.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

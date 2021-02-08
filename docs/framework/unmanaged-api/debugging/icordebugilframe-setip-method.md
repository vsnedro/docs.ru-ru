---
description: 'Дополнительные сведения о методе: ICorDebugILFrame:: SetIP'
title: Метод ICorDebugILFrame::SetIP
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::SetIP
helpviewer_keywords:
- SetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::SetIP method [.NET Framework debugging]
ms.assetid: 23f38dc1-85e4-4263-9235-2d05bbb6a833
topic_type:
- apiref
ms.openlocfilehash: 75d2530a3d9151c64980316757074141776a78d3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791326"
---
# <a name="icordebugilframesetip-method"></a>Метод ICorDebugILFrame::SetIP

Задает указатель инструкции в указанном расположении смещения в коде промежуточного языка Майкрософт (MSIL).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `nOffset`  
 Положение смещения в коде MSIL.  
  
## <a name="remarks"></a>Remarks  

 Вызывает метод, чтобы `SetIP` немедленно сделать недействительными все кадры и цепочки для текущего потока. Если отладчику требуются сведения о кадре после вызова `SetIP` , он должен выполнить новую трассировку стека.  
  
 [ICorDebug](icordebug-interface.md) попытается удержать кадр стека в допустимом состоянии. Тем не менее, даже если кадр находится в допустимом состоянии, могут возникнуть проблемы, например неинициализированные локальные переменные. Вызывающий объект отвечает за обеспечение согласованности выполняющейся программы.  
  
 На 64-разрядных платформах указатель инструкции не может быть перемещен из `catch` блока или `finally` . Если `SetIP` вызывается метод для перемещения на 64-разрядной платформе, он возвращает значение HRESULT, указывающее на сбой.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

---
description: 'Дополнительные сведения о методе: ICorDebugILFrame:: Енумерателокалвариаблес'
title: Метод ICorDebugILFrame::EnumerateLocalVariables
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
ms.openlocfilehash: 275cf7fcad32c452e6e7ebdd0774d64708a2398c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791391"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a>Метод ICorDebugILFrame::EnumerateLocalVariables

Возвращает перечислитель для локальных переменных в этом кадре.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ppValueEnum`  
 [из] Указатель на адрес объекта ICorDebugValueEnum, который является перечислителем для локальных переменных в этом кадре.  
  
## <a name="remarks"></a>Remarks  

 `EnumerateLocalVariables` Возвращает перечислитель, который может перечислить локальные переменные, доступные в кадре вызова, представленном этим объектом ICorDebugILFrame. Список не может включать все локальные переменные в выполняемой функции, так как некоторые из них могут быть неактивными.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

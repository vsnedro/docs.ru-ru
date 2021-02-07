---
description: 'Дополнительные сведения о методе: ICoreClrDebugTarget:: FreeMemory'
title: Метод ICoreClrDebugTarget::FreeMemory
ms.date: 03/30/2017
api_name:
- ICoreDebugTarget.FreeMemory
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::FreeMemory
helpviewer_keywords:
- remote debugging API [Silverlight]
- FreeMemory method, ICoreClrDebugTarget interface [Silverlight debugging]
- ICorClrDebugTarget::FreeMemory method [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 98f2a0db-a6ec-4f9b-861d-f82485237d08
topic_type:
- apiref
ms.openlocfilehash: 9572e0c3df1fdd064e78ba170d39c1415c68dc85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690006"
---
# <a name="icoreclrdebugtargetfreememory-method"></a>Метод ICoreClrDebugTarget::FreeMemory

Освобождает память, выделенную методам [ICoreClrDebugTarget:: EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) и [ICoreClrDebugTarget:: EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void FreeMemory (  
     [in] void*pMemory);  
```  
  
## <a name="parameters"></a>Параметры  

 `pMemory`  
 окне Указатель на массив, возвращаемый методом [ICoreClrDebugTarget:: EnumProcesses](icoreclrdebugtarget-enumprocesses-method.md) или [ICoreClrDebugTarget:: EnumRuntimes](icoreclrdebugtarget-enumruntimes-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Кореклрремотедебуггингинтерфацес. h  
  
 **Библиотека:** mscordbi_macx86.dll  
  
 **Платформа .NET Framework версии:** 3,5 SP1  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICoreClrDebugTarget](icoreclrdebugtarget-interface.md)

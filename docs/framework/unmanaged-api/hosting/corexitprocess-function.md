---
description: Дополнительные сведения о функции Корекситпроцесс
title: Функция CorExitProcess
ms.date: 03/30/2017
api_name:
- CorExitProcess
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CorExitProcess
helpviewer_keywords:
- CorExitProcess function [.NET Framework hosting]
ms.assetid: a5cab4c6-990e-47f3-8798-cf422b791015
topic_type:
- apiref
ms.openlocfilehash: 68d33dec76387e103a34e99c529a4e7aff7535b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649589"
---
# <a name="corexitprocess-function"></a>Функция CorExitProcess

Завершает текущий неуправляемый процесс.  
  
 Эта функция является устаревшей в платформа .NET Framework 4. Используйте вместо этого метод [ICLRMetaHost:: ExitProcess](iclrmetahost-exitprocess-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void STDMETHODCALLTYPE CorExitProcess (
  int  exitCode  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `exitCode`  
 Целое число, указывающее код завершения процесса.  
  
## <a name="remarks"></a>Remarks  
  
> [!NOTE]
> Начиная с платформа .NET Framework 4, `CorExitProcess` завершает каждую запущенную среду выполнения в процессе, а не только среду выполнения, к которой привязаны API прежних версий.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

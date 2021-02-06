---
description: 'Дополнительные сведения о методе: ICorDebugModule:: Исинмемори'
title: Метод ICorDebugModule::IsInMemory
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
ms.openlocfilehash: 41454ede15e1d45775af8fb0ab7a6b571d9c0e41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660093"
---
# <a name="icordebugmoduleisinmemory-method"></a>Метод ICorDebugModule::IsInMemory

Возвращает значение, указывающее, существует ли этот модуль только в памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pInMemory`  
 [out] `true` значение, если этот модуль существует только в памяти; в противном случае — `false` .  
  
## <a name="remarks"></a>Remarks  

 Среда CLR поддерживает загрузку модулей из необработанных потоков байтов. Такие модули называются *модулями в памяти* и не существуют на диске.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

---
description: Дополнительные сведения о перечислении Есимболреадингполици
title: Перечисление ESymbolReadingPolicy
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
ms.openlocfilehash: e84c31343b589cb6019d88fafc9b94207c5f5892
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785423"
---
# <a name="esymbolreadingpolicy-enumeration"></a>Перечисление ESymbolReadingPolicy

Содержит значения, задают политику чтения PDB-файлов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`eSymbolReadingAlways`|Указывает, что отладчик всегда должен считывать PDB-файлы.|  
|`eSymbolReadingFullTrustOnly`|Указывает, что отладчик должен считывать только PDB-файлы, связанные со сборками с полным доверием.|  
|`eSymbolReadingNever`|Указывает, что отладчик никогда не должен считывать PDB-файлы.|  
  
## <a name="remarks"></a>Remarks  

 `ESymbolReadingPolicy`Перечисление используется с методом [ICLRDebugManager:: SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение перечислений](hosting-enumerations.md)

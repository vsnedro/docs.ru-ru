---
title: Функция GetCachePath
ms.date: 03/30/2017
api_name:
- GetCachePath
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- GetCachePath
helpviewer_keywords:
- GetCachePath function [.NET Framework fusion]
ms.assetid: d977ad29-6619-42e1-b0be-bc25ea950e80
topic_type:
- apiref
ms.openlocfilehash: c22f0701cfda4523f595366a97435ef8da08b0cb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724472"
---
# <a name="getcachepath-function"></a>Функция GetCachePath

Возвращает путь к кэшированной сборке с использованием указанных флагов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCachePath (  
    [in]      ASM_CACHE_FLAGS  dwCacheFlags,  
    [in]      LPWSTR           pwzCachePath,  
    [in, out] PDWORD           pcchPath  
 );  
```  
  
## <a name="parameters"></a>Параметры  

 `dwCacheFlags`  
 окне Значение [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) , указывающее источник кэшированной сборки.  
  
 `pwzCachePath`  
 заполняет Возвращаемый указатель на путь.  
  
 `pcchPath`  
 [вход, выход] Запрошенная максимальная длина `pwzCachePath` и при возврате фактической длины `pwzCachePath` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисление ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)

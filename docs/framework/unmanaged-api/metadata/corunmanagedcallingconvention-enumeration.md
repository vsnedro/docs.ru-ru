---
title: Перечисление CorUnmanagedCallingConvention
ms.date: 03/30/2017
api_name:
- CorUnmanagedCallingConvention
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorUnmanagedCallingConvention
helpviewer_keywords:
- CorUnmanagedCallingConvention enumeration [.NET Framework metadata]
ms.assetid: 83058790-160b-4703-a5eb-74b66acbdfa9
topic_type:
- apiref
ms.openlocfilehash: 9d35f6b1928d714216b669704ec28e53895f6549
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699070"
---
# <a name="corunmanagedcallingconvention-enumeration"></a>Перечисление CorUnmanagedCallingConvention

Указывает соглашения о вызовах для неуправляемого кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorUnmanagedCallingConvention {  
  
    IMAGE_CEE_UNMANAGED_CALLCONV_C         = 0x1,  
    IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL   = 0x2,  
    IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL  = 0x3,  
    IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL  = 0x4,  
  
    IMAGE_CEE_CS_CALLCONV_C                = 0x1,  
    IMAGE_CEE_CS_CALLCONV_STDCALL          = 0x2,  
    IMAGE_CEE_CS_CALLCONV_THISCALL         = 0x3,  
    IMAGE_CEE_CS_CALLCONV_FASTCALL         = 0x4  
  
} CorUnmanagedCallingConvention;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_C`|Соглашение о вызовах языка C.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_STDCALL`|Стандартное соглашение о вызовах.|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_THISCALL`|Соглашение о вызовах "this".|  
|`IMAGE_CEE_UNMANAGED_CALLCONV_FASTCALL`|Соглашение о вызовах "Fast".|  
|`IMAGE_CEE_CS_CALLCONV_C`|Не используется.|  
|`IMAGE_CEE_CS_CALLCONV_STDCALL`|Не используется.|  
|`IMAGE_CEE_CS_CALLCONV_THISCALL`|Не используется.|  
|`IMAGE_CEE_CS_CALLCONV_FASTCALL`|Не используется.|  
  
## <a name="remarks"></a>Комментарии  

 Среда CLR не поддерживает "быстрое" соглашение о вызовах в .NET Framework версии 1,0.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](metadata-enumerations.md)

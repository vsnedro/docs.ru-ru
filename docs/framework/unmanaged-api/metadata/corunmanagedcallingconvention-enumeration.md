---
description: Дополнительные сведения о перечислении Корунманажедкаллингконвентион
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
ms.openlocfilehash: a4b5c70b7dcb4750d641540662941ed3cc08c94b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707297"
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
  
## <a name="remarks"></a>Remarks  

 Среда CLR не поддерживает "быстрое" соглашение о вызовах в платформа .NET Framework версии 1,0.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](metadata-enumerations.md)

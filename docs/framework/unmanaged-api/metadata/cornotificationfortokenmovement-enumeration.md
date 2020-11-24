---
title: Перечисление CorNotificationForTokenMovement
ms.date: 03/30/2017
api_name:
- CorNotificationForTokenMovement
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNotificationForTokenMovement
helpviewer_keywords:
- CorNotificationForTokenMovement enumeration [.NET Framework metadata]
ms.assetid: 1edd1670-976a-4fc8-bef7-7c41e60ad989
topic_type:
- apiref
ms.openlocfilehash: 0f9cb8db35a1669cead6f9f26c9a89e063628dd8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687675"
---
# <a name="cornotificationfortokenmovement-enumeration"></a>Перечисление CorNotificationForTokenMovement

Указывает уведомления, которые будут отправляться клиенту API метаданных при выполнении сопоставления маркеров.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorNotificationForTokenMovement {  
  
    MDNotifyDefault             = 0x0000000f,  
    MDNotifyAll                 = 0xffffffff,  
    MDNotifyNone                = 0x00000000,  
    MDNotifyMethodDef           = 0x00000001,  
    MDNotifyMemberRef           = 0x00000002,  
    MDNotifyFieldDef            = 0x00000004,  
    MDNotifyTypeRef             = 0x00000008,  
  
    MDNotifyTypeDef             = 0x00000010,  
    MDNotifyParamDef            = 0x00000020,  
    MDNotifyInterfaceImpl       = 0x00000040,  
    MDNotifyProperty            = 0x00000080,  
    MDNotifyEvent               = 0x00000100,  
    MDNotifySignature           = 0x00000200,  
    MDNotifyTypeSpec            = 0x00000400,  
    MDNotifyCustomAttribute     = 0x00000800,  
    MDNotifySecurityValue       = 0x00001000,  
    MDNotifyPermission          = 0x00002000,  
    MDNotifyModuleRef           = 0x00004000,  
  
    MDNotifyNameSpace           = 0x00008000,  
  
    MDNotifyAssemblyRef         = 0x01000000,  
    MDNotifyFile                = 0x02000000,  
    MDNotifyExportedType        = 0x04000000,  
    MDNotifyResource            = 0x08000000  
  
} CorNotificationForTokenMovement;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`MDNotifyDefault`|Уведомлять при `mdTypeRef` `mdMethodDef` `mdMemberRef` `mdFieldDef` перемещении токенов,, или.|  
|`MDNotifyAll`|Уведомлять при перемещении токена.|  
|`MDNotifyNone`|Не уведомлять при перемещении токенов.|  
|`MDNotifyMethodDef`|Уведомлять при `mdMethodDef` перемещении маркера.|  
|`MDNotifyMemberRef`|Уведомлять при `mdMemberRef` перемещении маркера.|  
|`MDNotifyFieldDef`|Уведомлять при `mdFieldDef` перемещении маркера.|  
|`MDNotifyTypeRef`|Уведомлять при `mdTypeRef` перемещении маркера.|  
|`MDNotifyTypeDef`|Уведомлять при `mdTypeDef` перемещении маркера.|  
|`MDNotifyParamDef`|Уведомлять при `mdParamDef` перемещении маркера.|  
|`MDNotifyInterfaceImpl`|Уведомлять при `mdInterfaceImpl` перемещении маркера.|  
|`MDNotifyProperty`|Уведомлять при `mdProperty` перемещении маркера.|  
|`MDNotifyEvent`|Уведомлять при `mdEvent` перемещении маркера.|  
|`MDNotifySignature`|Уведомлять при `mdSignature` перемещении маркера.|  
|`MDNotifyTypeSpec`|Уведомлять при `mdTypeSpec` перемещении маркера.|  
|`MDNotifyCustomAttribute`|Уведомлять при `mdCustomAttribute` перемещении маркера.|  
|`MDNotifySecurityValue`|Уведомлять при `mdSecurityValue` перемещении маркера.|  
|`MDNotifyPermission`|Уведомлять при `mdPermission` перемещении маркера.|  
|`MDNotifyModuleRef`|Уведомлять при `mdModuleRef` перемещении маркера.|  
|`MDNotifyNameSpace`|Уведомлять при `mdNameSpace` перемещении маркера.|  
|`MDNotifyAssemblyRef`|Уведомлять при `mdAssemblyRef` перемещении маркера.|  
|`MDNotifyFile`|Уведомлять при `mdFile` перемещении маркера.|  
|`MDNotifyExportedType`|Уведомлять при `mdExportedType` перемещении маркера.|  
|`MDNotifyResource`|Уведомлять при `mdManifestResource` перемещении маркера.|  
  
## <a name="remarks"></a>Комментарии  

 Маркер может быть повторно сопоставлен (т. е. перемещен) во время слияния метаданных.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Корхдр. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Перечисления метаданных](metadata-enumerations.md)

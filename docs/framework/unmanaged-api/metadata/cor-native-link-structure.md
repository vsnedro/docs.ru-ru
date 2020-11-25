---
title: Структура COR_NATIVE_LINK
ms.date: 03/30/2017
api_name:
- COR_NATIVE_LINK
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_NATIVE_LINK
helpviewer_keywords:
- COR_NATIVE_LINK structure [.NET Framework metadata]
ms.assetid: 6ef78d3c-1c69-4141-b687-dcb065b7a74d
topic_type:
- apiref
ms.openlocfilehash: 15f573ebc07bcf08a1ab8f5a5bbb88e940c5c8dc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724173"
---
# <a name="cor_native_link-structure"></a>Структура COR_NATIVE_LINK

Содержит сведения, используемые для связи с машинным кодом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`m_linkType`|Тип, который должен быть связан в машинном коде. Это значение является одним из значений [корнативелинктипе](cornativelinktype-enumeration.md) .|  
|`m_flags`|Флаги, используемые компоновщиком при связывании машинного кода. Это значение является одним из значений [CorNativeLinkFlags](cornativelinkflags-enumeration.md) .|  
|`m_entryPoint`|Токен метаданных MemberRef, представляющий точку входа. Формат — `lib:entrypoint`.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Структуры метаданных](metadata-structures.md)
- [Перечисление CorNativeLinkType](cornativelinktype-enumeration.md)
- [Перечисление CorNativeLinkFlags](cornativelinkflags-enumeration.md)

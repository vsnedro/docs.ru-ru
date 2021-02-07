---
description: 'Дополнительные сведения: структура COR_NATIVE_LINK'
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
ms.openlocfilehash: 09c715af698a0614fd4a9a17679df6908a1497a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678579"
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
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Структуры метаданных](metadata-structures.md)
- [Перечисление CorNativeLinkType](cornativelinktype-enumeration.md)
- [Перечисление CorNativeLinkFlags](cornativelinkflags-enumeration.md)

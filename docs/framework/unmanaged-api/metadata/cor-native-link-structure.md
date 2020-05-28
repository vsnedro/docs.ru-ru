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
ms.openlocfilehash: a11b7d5939c4c20504b1ff3dfb4613f85bca0db4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007979"
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`m_linkType`|Тип, который должен быть связан в машинном коде. Это значение является одним из значений [корнативелинктипе](cornativelinktype-enumeration.md) .|  
|`m_flags`|Флаги, используемые компоновщиком при связывании машинного кода. Это значение является одним из значений [CorNativeLinkFlags](cornativelinkflags-enumeration.md) .|  
|`m_entryPoint`|Токен метаданных MemberRef, представляющий точку входа. Формат — `lib:entrypoint`.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Структуры метаданных](metadata-structures.md)
- [Перечисление CorNativeLinkType](cornativelinktype-enumeration.md)
- [Перечисление CorNativeLinkFlags](cornativelinkflags-enumeration.md)

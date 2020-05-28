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
# <a name="cor_native_link-structure"></a><span data-ttu-id="4ebbc-102">Структура COR_NATIVE_LINK</span><span class="sxs-lookup"><span data-stu-id="4ebbc-102">COR_NATIVE_LINK Structure</span></span>
<span data-ttu-id="4ebbc-103">Содержит сведения, используемые для связи с машинным кодом.</span><span class="sxs-lookup"><span data-stu-id="4ebbc-103">Contains information that is used to link native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ebbc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ebbc-104">Syntax</span></span>  
  
```cpp  
typedef struct
{  
    BYTE        m_linkType;  
    BYTE        m_flags;  
    mdMemberRef m_entryPoint;  
} COR_NATIVE_LINK;  
```  
  
## <a name="members"></a><span data-ttu-id="4ebbc-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4ebbc-105">Members</span></span>  
  
|<span data-ttu-id="4ebbc-106">Член</span><span class="sxs-lookup"><span data-stu-id="4ebbc-106">Member</span></span>|<span data-ttu-id="4ebbc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4ebbc-107">Description</span></span>|  
|------------|-----------------|  
|`m_linkType`|<span data-ttu-id="4ebbc-108">Тип, который должен быть связан в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="4ebbc-108">The type to be linked in native code.</span></span> <span data-ttu-id="4ebbc-109">Это значение является одним из значений [корнативелинктипе](cornativelinktype-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="4ebbc-109">This value is one of the [CorNativeLinkType](cornativelinktype-enumeration.md) values.</span></span>|  
|`m_flags`|<span data-ttu-id="4ebbc-110">Флаги, используемые компоновщиком при связывании машинного кода.</span><span class="sxs-lookup"><span data-stu-id="4ebbc-110">Flags used by the linker when linking native code.</span></span> <span data-ttu-id="4ebbc-111">Это значение является одним из значений [CorNativeLinkFlags](cornativelinkflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="4ebbc-111">This value is one of the [CorNativeLinkFlags](cornativelinkflags-enumeration.md) values.</span></span>|  
|`m_entryPoint`|<span data-ttu-id="4ebbc-112">Токен метаданных MemberRef, представляющий точку входа.</span><span class="sxs-lookup"><span data-stu-id="4ebbc-112">The MemberRef metadata token that represents the entry point.</span></span> <span data-ttu-id="4ebbc-113">Формат — `lib:entrypoint`.</span><span class="sxs-lookup"><span data-stu-id="4ebbc-113">The format is `lib:entrypoint`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4ebbc-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4ebbc-114">Requirements</span></span>  
 <span data-ttu-id="4ebbc-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ebbc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ebbc-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="4ebbc-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4ebbc-117">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4ebbc-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4ebbc-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4ebbc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ebbc-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="4ebbc-119">See also</span></span>

- [<span data-ttu-id="4ebbc-120">Структуры метаданных</span><span class="sxs-lookup"><span data-stu-id="4ebbc-120">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="4ebbc-121">Перечисление CorNativeLinkType</span><span class="sxs-lookup"><span data-stu-id="4ebbc-121">CorNativeLinkType Enumeration</span></span>](cornativelinktype-enumeration.md)
- [<span data-ttu-id="4ebbc-122">Перечисление CorNativeLinkFlags</span><span class="sxs-lookup"><span data-stu-id="4ebbc-122">CorNativeLinkFlags Enumeration</span></span>](cornativelinkflags-enumeration.md)

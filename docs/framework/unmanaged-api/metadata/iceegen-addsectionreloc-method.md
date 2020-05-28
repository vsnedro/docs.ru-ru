---
title: Метод ICeeGen::AddSectionReloc
ms.date: 03/30/2017
api_name:
- ICeeGen.AddSectionReloc
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::AddSectionReloc
helpviewer_keywords:
- AddSectionReloc method [.NET Framework metadata]
- ICeeGen::AddSectionReloc method [.NET Framework metadata]
ms.assetid: b500a260-1d57-4953-95e1-c27063f7c8da
topic_type:
- apiref
ms.openlocfilehash: 2f66d34fcfdd8c61dcc92817ec1a928ac5b603fc
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008902"
---
# <a name="iceegenaddsectionreloc-method"></a><span data-ttu-id="df6f8-102">Метод ICeeGen::AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="df6f8-102">ICeeGen::AddSectionReloc Method</span></span>
<span data-ttu-id="df6f8-103">Добавляет инструкцию. reloc в базу кода.</span><span class="sxs-lookup"><span data-stu-id="df6f8-103">Adds a .reloc instruction to the code base.</span></span>  
  
 <span data-ttu-id="df6f8-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="df6f8-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df6f8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df6f8-105">Syntax</span></span>  
  
```cpp  
HRESULT AddSectionReloc (  
   [in] HCEESECTION            section,  
   [in] ULONG                  offset,  
   [in] HCEESECTION            relativeTo,
   [in] CeeSectionRelocType    relocType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df6f8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="df6f8-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="df6f8-107">окне Раздел кода в памяти, к которому добавляется инструкция. reloc.</span><span class="sxs-lookup"><span data-stu-id="df6f8-107">[in] The section of in-memory code to which to add a .reloc instruction.</span></span>  
  
 `offset`  
 <span data-ttu-id="df6f8-108">окне Смещение раздела.</span><span class="sxs-lookup"><span data-stu-id="df6f8-108">[in] The offset of the section.</span></span>  
  
 `relativeTo`  
 <span data-ttu-id="df6f8-109">окне Раздел, на который `offset` ссылается.</span><span class="sxs-lookup"><span data-stu-id="df6f8-109">[in] The section to which `offset` refers.</span></span>  
  
 `relocType`  
 <span data-ttu-id="df6f8-110">окне Одно из значений [цеесектионрелоктипе](ceesectionreloctype-enumeration.md) , указывающее тип добавляемой инструкции. reloc.</span><span class="sxs-lookup"><span data-stu-id="df6f8-110">[in] One of the [CeeSectionRelocType](ceesectionreloctype-enumeration.md) values, indicating the kind of .reloc instruction to add.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df6f8-111">Требования</span><span class="sxs-lookup"><span data-stu-id="df6f8-111">Requirements</span></span>  
 <span data-ttu-id="df6f8-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df6f8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df6f8-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="df6f8-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="df6f8-114">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="df6f8-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="df6f8-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df6f8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df6f8-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="df6f8-116">See also</span></span>

- [<span data-ttu-id="df6f8-117">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="df6f8-117">ICeeGen Interface</span></span>](iceegen-interface.md)

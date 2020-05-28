---
title: Перечисление CeeSectionRelocType
ms.date: 03/30/2017
api_name:
- CeeSectionRelocType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CeeSectionRelocType
helpviewer_keywords:
- CeeSectionRelocType enumeration [.NET Framework metadata]
ms.assetid: 124656f6-0dad-4ceb-9043-d3869ab65cde
topic_type:
- apiref
ms.openlocfilehash: 78b30f624bd71234e8f1b56600b3a23d15fdf517
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006039"
---
# <a name="ceesectionreloctype-enumeration"></a><span data-ttu-id="62bda-102">Перечисление CeeSectionRelocType</span><span class="sxs-lookup"><span data-stu-id="62bda-102">CeeSectionRelocType Enumeration</span></span>
<span data-ttu-id="62bda-103">Предоставляет значения, влияющие на тип `reloc` инструкции, выдаваемой при вызове метода [ICeeGen:: AddSectionReloc](iceegen-addsectionreloc-method.md).</span><span class="sxs-lookup"><span data-stu-id="62bda-103">Provides values to influence the type of `reloc` instruction emitted in a call to [ICeeGen::AddSectionReloc](iceegen-addsectionreloc-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62bda-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62bda-104">Syntax</span></span>  
  
```cpp  
typedef enum  {  
    srRelocAbsolute,  
    srRelocHighLow          = 3,  
    srRelocHighAdj,
    srRelocMapToken,  
    srRelocRelative,  
    srRelocFilePos,  
    srRelocCodeRelative,  
    srRelocIA64Imm64,  
    srRelocDir64,  
    srRelocIA64PcRel25,  
    srRelocIA64PcRel64,    srRelocAbsoluteTagged,    srRelocSentinel,    srNoBaseReloc       = 0x4000,  
    srRelocPtr          = 0x8000,  
    srRelocAbsolutePtr      = srRelocPtr + srRelocAbsolute,  
    srRelocHighLowPtr       = srRelocPtr + srRelocHighLow,  
    srRelocRelativePtr      = srRelocPtr + srRelocRelative,  
    srRelocIA64Imm64Ptr     = srRelocPtr + srRelocIA64Imm64,  
    srRelocDir64Ptr         = srRelocPtr + srRelocDir64  
    } CeeSectionRelocType;  
```  
  
## <a name="members"></a><span data-ttu-id="62bda-105">Участники</span><span class="sxs-lookup"><span data-stu-id="62bda-105">Members</span></span>  
  
|<span data-ttu-id="62bda-106">Член</span><span class="sxs-lookup"><span data-stu-id="62bda-106">Member</span></span>|<span data-ttu-id="62bda-107">Описание</span><span class="sxs-lookup"><span data-stu-id="62bda-107">Description</span></span>|  
|------------|-----------------|  
|`srRelocAbsolute`|<span data-ttu-id="62bda-108">Создает только относительный раздел `reloc` , отправляя в раздел. reloc ничего.</span><span class="sxs-lookup"><span data-stu-id="62bda-108">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span>|  
|`srRelocHighLow`|<span data-ttu-id="62bda-109">Создает `reloc` для расположения, размер которого определяется указателем.</span><span class="sxs-lookup"><span data-stu-id="62bda-109">Generates a `reloc` for a pointer-sized location.</span></span> <span data-ttu-id="62bda-110">Он преобразуется в BASED_HIGHLOW или BASED_DIR64 в зависимости от платформы.</span><span class="sxs-lookup"><span data-stu-id="62bda-110">This is transformed into BASED_HIGHLOW or BASED_DIR64 depending on the platform.</span></span>|  
|`srRelocHighAdj`|<span data-ttu-id="62bda-111">Создает `reloc` для старших 16 бит 32-разрядного числа, где 16 нижних бит включены в следующее слово в таблице. reloc.</span><span class="sxs-lookup"><span data-stu-id="62bda-111">Generates a `reloc` for the top 16 bits of a 32-bit number, where the bottom 16 bits are included in the next word in the .reloc table.</span></span>|  
|`srRelocMapToken`|<span data-ttu-id="62bda-112">Создает перемещение карт маркеров, отправляя в раздел. reloc значение Nothing.</span><span class="sxs-lookup"><span data-stu-id="62bda-112">Generates a token map relocation, sending nothing into a .reloc section.</span></span>|  
|`srRelocRelative`|<span data-ttu-id="62bda-113">Указывает, что значением является адресная привязка относительных адресов.</span><span class="sxs-lookup"><span data-stu-id="62bda-113">Indicates that the value is a relative address fixup.</span></span>|  
|`srRelocFilePos`|<span data-ttu-id="62bda-114">Создает только относительный раздел `reloc` , отправляя в раздел. reloc ничего.</span><span class="sxs-lookup"><span data-stu-id="62bda-114">Generates only a section-relative `reloc`, sending nothing into a .reloc section.</span></span> <span data-ttu-id="62bda-115">Это `reloc` относится к расположению файла в разделе, а не к виртуальному адресу раздела.</span><span class="sxs-lookup"><span data-stu-id="62bda-115">This `reloc` is relative to the file position of the section, not the section's virtual address.</span></span>|  
|`srRelocCodeRelative`|<span data-ttu-id="62bda-116">Указывает адресную привязку адреса, относительную для кода.</span><span class="sxs-lookup"><span data-stu-id="62bda-116">Specifies a code-relative address fixup.</span></span>|  
|`srRelocIA64Imm64`|<span data-ttu-id="62bda-117">Создает `reloc` для 64-разрядного адреса в инструкции ia64 `movl` .</span><span class="sxs-lookup"><span data-stu-id="62bda-117">Generates a `reloc` for a 64 bit address in an ia64 `movl` instruction.</span></span>|  
|`srRelocDir64`|<span data-ttu-id="62bda-118">Создает `reloc` для 64-разрядного адреса.</span><span class="sxs-lookup"><span data-stu-id="62bda-118">Generates a `reloc` for a 64-bit address.</span></span>|  
|`srRelocIA64PcRel25`|<span data-ttu-id="62bda-119">Создание `reloc` для 25-разрядного адреса, относительного для ПК, в `br.call` инструкции IA64.</span><span class="sxs-lookup"><span data-stu-id="62bda-119">Generate a `reloc` for a 25-bit PC-relative address in an ia64 `br.call` instruction.</span></span>|  
|`srRelocIA64PcRel64`|<span data-ttu-id="62bda-120">Создает `reloc` для 64-разрядного адреса, относительный для ПК, в `brl.call` инструкции IA64.</span><span class="sxs-lookup"><span data-stu-id="62bda-120">Generates a `reloc` for a 64-bit PC-relative address in an ia64 `brl.call` instruction.</span></span>|  
|`srRelocAbsoluteTagged`|<span data-ttu-id="62bda-121">Формирует 30-разрядный раздел относительно `reloc` значений указателей с тегами.</span><span class="sxs-lookup"><span data-stu-id="62bda-121">Generates a 30-bit section-relative `reloc`, used for tagged pointer values.</span></span>|  
|`srRelocSentinel`|<span data-ttu-id="62bda-122">Значение Sentinel, которое помогает гарантировать, что все дополнения к этому перечислению отражаются в `reloc` массиве внутренних имен.</span><span class="sxs-lookup"><span data-stu-id="62bda-122">A sentinel value to help ensure any additions to this enum are reflected to the internal `reloc` name array.</span></span>|  
|`srNoBaseReloc`|<span data-ttu-id="62bda-123">Указывает, что не следует создавать базу `reloc` .</span><span class="sxs-lookup"><span data-stu-id="62bda-123">Specifies not to emit a base `reloc`.</span></span>|  
|`srRelocPtr`|<span data-ttu-id="62bda-124">Значение, указывающее, что предварительная адресная привязка содержимого памяти является указателем, а не смещением раздела.</span><span class="sxs-lookup"><span data-stu-id="62bda-124">A value indicating that the pre-fixup contents of memory are a pointer rather than a section offset.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="62bda-125">Требования</span><span class="sxs-lookup"><span data-stu-id="62bda-125">Requirements</span></span>  
 <span data-ttu-id="62bda-126">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62bda-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62bda-127">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="62bda-127">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62bda-128">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="62bda-128">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62bda-129">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62bda-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62bda-130">См. также статью</span><span class="sxs-lookup"><span data-stu-id="62bda-130">See also</span></span>

- [<span data-ttu-id="62bda-131">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="62bda-131">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="62bda-132">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="62bda-132">ICeeGen Interface</span></span>](iceegen-interface.md)
- [<span data-ttu-id="62bda-133">Метод AddSectionReloc</span><span class="sxs-lookup"><span data-stu-id="62bda-133">AddSectionReloc Method</span></span>](iceegen-addsectionreloc-method.md)

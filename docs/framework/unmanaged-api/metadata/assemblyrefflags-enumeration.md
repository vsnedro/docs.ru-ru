---
title: Перечисление AssemblyRefFlags
ms.date: 03/30/2017
api_name:
- AssemblyRefFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AssemblyRefFlags
helpviewer_keywords:
- AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type:
- apiref
ms.openlocfilehash: 0a99d2f79645bdc46ff4db86d7280614eeb1faf5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732766"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="bf44b-102">Перечисление AssemblyRefFlags</span><span class="sxs-lookup"><span data-stu-id="bf44b-102">AssemblyRefFlags Enumeration</span></span>

<span data-ttu-id="bf44b-103">Содержит значения, описывающие функции ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="bf44b-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf44b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf44b-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="bf44b-105">Члены</span><span class="sxs-lookup"><span data-stu-id="bf44b-105">Members</span></span>  
  
|<span data-ttu-id="bf44b-106">Член</span><span class="sxs-lookup"><span data-stu-id="bf44b-106">Member</span></span>|<span data-ttu-id="bf44b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="bf44b-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="bf44b-108">Указывает, что ссылка на сборку содержит полные нехэшированные сведения об издателе сборки.</span><span class="sxs-lookup"><span data-stu-id="bf44b-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bf44b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="bf44b-109">Requirements</span></span>  

 <span data-ttu-id="bf44b-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf44b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf44b-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="bf44b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bf44b-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf44b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf44b-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="bf44b-113">See also</span></span>

- [<span data-ttu-id="bf44b-114">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="bf44b-114">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="bf44b-115">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="bf44b-115">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="bf44b-116">Метод DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="bf44b-116">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)

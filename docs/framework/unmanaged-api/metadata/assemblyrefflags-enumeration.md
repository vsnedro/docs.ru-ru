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
ms.openlocfilehash: 1307f555c9d8b6d28febcf25db89ae856c143d71
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009409"
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="c2b8a-102">Перечисление AssemblyRefFlags</span><span class="sxs-lookup"><span data-stu-id="c2b8a-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="c2b8a-103">Содержит значения, описывающие функции ссылки на сборку.</span><span class="sxs-lookup"><span data-stu-id="c2b8a-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2b8a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2b8a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="c2b8a-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c2b8a-105">Members</span></span>  
  
|<span data-ttu-id="c2b8a-106">Член</span><span class="sxs-lookup"><span data-stu-id="c2b8a-106">Member</span></span>|<span data-ttu-id="c2b8a-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c2b8a-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="c2b8a-108">Указывает, что ссылка на сборку содержит полные нехэшированные сведения об издателе сборки.</span><span class="sxs-lookup"><span data-stu-id="c2b8a-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2b8a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c2b8a-109">Requirements</span></span>  
 <span data-ttu-id="c2b8a-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2b8a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2b8a-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c2b8a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2b8a-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2b8a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b8a-113">См. также статью</span><span class="sxs-lookup"><span data-stu-id="c2b8a-113">See also</span></span>

- [<span data-ttu-id="c2b8a-114">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="c2b8a-114">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="c2b8a-115">Интерфейс IMetaDataAssemblyEmit</span><span class="sxs-lookup"><span data-stu-id="c2b8a-115">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="c2b8a-116">Метод DefineAssemblyRef</span><span class="sxs-lookup"><span data-stu-id="c2b8a-116">DefineAssemblyRef Method</span></span>](imetadataassemblyemit-defineassemblyref-method.md)

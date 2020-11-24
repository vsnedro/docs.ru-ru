---
title: Перечисление CorFileFlags
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
ms.openlocfilehash: 70d789f417700734b546cac6ff527ed5aa84fcf9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688631"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="0faeb-102">Перечисление CorFileFlags</span><span class="sxs-lookup"><span data-stu-id="0faeb-102">CorFileFlags Enumeration</span></span>

<span data-ttu-id="0faeb-103">Содержит значения, описывающие тип файла, определенного в вызове [IMetaDataAssemblyEmit::D ефинефиле](imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="0faeb-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0faeb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0faeb-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="0faeb-105">Члены</span><span class="sxs-lookup"><span data-stu-id="0faeb-105">Members</span></span>  
  
|<span data-ttu-id="0faeb-106">Член</span><span class="sxs-lookup"><span data-stu-id="0faeb-106">Member</span></span>|<span data-ttu-id="0faeb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="0faeb-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="0faeb-108">Указывает, что файл не является файлом ресурсов.</span><span class="sxs-lookup"><span data-stu-id="0faeb-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="0faeb-109">Указывает, что файл, возможно, файл ресурсов, не содержит метаданных.</span><span class="sxs-lookup"><span data-stu-id="0faeb-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0faeb-110">Требования</span><span class="sxs-lookup"><span data-stu-id="0faeb-110">Requirements</span></span>  

 <span data-ttu-id="0faeb-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0faeb-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0faeb-112">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="0faeb-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0faeb-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0faeb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0faeb-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0faeb-114">See also</span></span>

- [<span data-ttu-id="0faeb-115">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="0faeb-115">Metadata Enumerations</span></span>](metadata-enumerations.md)

---
title: Перечисление CorFileMapping
ms.date: 03/30/2017
api_name:
- CorFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileMapping
helpviewer_keywords:
- CorFileMapping enumeration [.NET Framework metadata]
ms.assetid: 3ca41592-b8da-475a-8032-a15627730003
topic_type:
- apiref
ms.openlocfilehash: 63e27a62e176a92b03c10b59a55d9da3192918f4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726121"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="96877-102">Перечисление CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="96877-102">CorFileMapping Enumeration</span></span>

<span data-ttu-id="96877-103">Содержит значения, описывающие тип сопоставления файлов, возвращаемого при вызове метода [иметадатаинфо:: GetFileMapping](imetadatainfo-getfilemapping-method.md) .</span><span class="sxs-lookup"><span data-stu-id="96877-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96877-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="96877-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="96877-105">Члены</span><span class="sxs-lookup"><span data-stu-id="96877-105">Members</span></span>  
  
|<span data-ttu-id="96877-106">Член</span><span class="sxs-lookup"><span data-stu-id="96877-106">Member</span></span>|<span data-ttu-id="96877-107">Описание</span><span class="sxs-lookup"><span data-stu-id="96877-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="96877-108">Файл сопоставляется как файл данных.</span><span class="sxs-lookup"><span data-stu-id="96877-108">The file is mapped as a data file.</span></span> <span data-ttu-id="96877-109">То есть `SEC_IMAGE` флаг не был передан функции Microsoft Win32 `CreateFileMapping` .</span><span class="sxs-lookup"><span data-stu-id="96877-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="96877-110">Файл сопоставляется для выполнения с помощью `LoadLibrary` функции или `CreateFileMapping` функции с `SEC_IMAGE` флагом.</span><span class="sxs-lookup"><span data-stu-id="96877-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="96877-111">Требования</span><span class="sxs-lookup"><span data-stu-id="96877-111">Requirements</span></span>  

 <span data-ttu-id="96877-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96877-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96877-113">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="96877-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="96877-114">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96877-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96877-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="96877-115">See also</span></span>

- [<span data-ttu-id="96877-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="96877-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="96877-117">Метод GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="96877-117">GetFileMapping Method</span></span>](imetadatainfo-getfilemapping-method.md)

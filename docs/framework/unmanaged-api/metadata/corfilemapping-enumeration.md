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
ms.openlocfilehash: 0ed1579886f1682348a136be3391f6bdc2543d26
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007394"
---
# <a name="corfilemapping-enumeration"></a><span data-ttu-id="650b7-102">Перечисление CorFileMapping</span><span class="sxs-lookup"><span data-stu-id="650b7-102">CorFileMapping Enumeration</span></span>
<span data-ttu-id="650b7-103">Содержит значения, описывающие тип сопоставления файлов, возвращаемого при вызове метода [иметадатаинфо:: GetFileMapping](imetadatainfo-getfilemapping-method.md) .</span><span class="sxs-lookup"><span data-stu-id="650b7-103">Contains values that describe the type of file mapping that is returned from a call to the [IMetaDataInfo::GetFileMapping](imetadatainfo-getfilemapping-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="650b7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="650b7-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileMapping {  
  
    fmFlat                  =   0x0000,  
    fmExecutableImage       =   0x0001  
  
} CorFileMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="650b7-105">Участники</span><span class="sxs-lookup"><span data-stu-id="650b7-105">Members</span></span>  
  
|<span data-ttu-id="650b7-106">Член</span><span class="sxs-lookup"><span data-stu-id="650b7-106">Member</span></span>|<span data-ttu-id="650b7-107">Описание</span><span class="sxs-lookup"><span data-stu-id="650b7-107">Description</span></span>|  
|------------|-----------------|  
|`fmFlat`|<span data-ttu-id="650b7-108">Файл сопоставляется как файл данных.</span><span class="sxs-lookup"><span data-stu-id="650b7-108">The file is mapped as a data file.</span></span> <span data-ttu-id="650b7-109">То есть `SEC_IMAGE` флаг не был передан функции Microsoft Win32 `CreateFileMapping` .</span><span class="sxs-lookup"><span data-stu-id="650b7-109">That is, the `SEC_IMAGE` flag was not passed to the Microsoft Win32 `CreateFileMapping` function.</span></span>|  
|`fmExecutableImage`|<span data-ttu-id="650b7-110">Файл сопоставляется для выполнения с помощью `LoadLibrary` функции или `CreateFileMapping` функции с `SEC_IMAGE` флагом.</span><span class="sxs-lookup"><span data-stu-id="650b7-110">The file is mapped for execution, by using either the `LoadLibrary` function or the `CreateFileMapping` function with the `SEC_IMAGE` flag.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="650b7-111">Требования</span><span class="sxs-lookup"><span data-stu-id="650b7-111">Requirements</span></span>  
 <span data-ttu-id="650b7-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="650b7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="650b7-113">**Заголовок:** Корхдр. h</span><span class="sxs-lookup"><span data-stu-id="650b7-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="650b7-114">**.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="650b7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="650b7-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="650b7-115">See also</span></span>

- [<span data-ttu-id="650b7-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="650b7-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
- [<span data-ttu-id="650b7-117">Метод GetFileMapping</span><span class="sxs-lookup"><span data-stu-id="650b7-117">GetFileMapping Method</span></span>](imetadatainfo-getfilemapping-method.md)

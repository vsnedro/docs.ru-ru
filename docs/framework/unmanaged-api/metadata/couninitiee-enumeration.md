---
title: Перечисление COUNINITIEE
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
ms.openlocfilehash: 14942680a79c4d1fcc69092a4f752738db1fb0b0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008924"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="f973b-102">Перечисление COUNINITIEE</span><span class="sxs-lookup"><span data-stu-id="f973b-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="f973b-103">Указывает константы, используемые [CoUninitializeEE](../hosting/couninitializeee-function.md) при инициализации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="f973b-103">Specifies constants used by [CoUninitializeEE](../hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f973b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f973b-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="f973b-105">Участники</span><span class="sxs-lookup"><span data-stu-id="f973b-105">Members</span></span>  
  
|<span data-ttu-id="f973b-106">Член</span><span class="sxs-lookup"><span data-stu-id="f973b-106">Member</span></span>|<span data-ttu-id="f973b-107">Описание</span><span class="sxs-lookup"><span data-stu-id="f973b-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="f973b-108">Указывает режим деинициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f973b-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="f973b-109">Указывает режим отмены инициализации для выгрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="f973b-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f973b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="f973b-110">Requirements</span></span>  
 <span data-ttu-id="f973b-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f973b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f973b-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f973b-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f973b-113">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f973b-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f973b-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f973b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f973b-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="f973b-115">See also</span></span>

- [<span data-ttu-id="f973b-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="f973b-116">Metadata Enumerations</span></span>](metadata-enumerations.md)

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
ms.openlocfilehash: b0f8c7e6d2acf4d4c080cc147bf6d42bf13cb51b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723835"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="e5d77-102">Перечисление COUNINITIEE</span><span class="sxs-lookup"><span data-stu-id="e5d77-102">COUNINITIEE Enumeration</span></span>

<span data-ttu-id="e5d77-103">Указывает константы, используемые [CoUninitializeEE](../hosting/couninitializeee-function.md) при инициализации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="e5d77-103">Specifies constants used by [CoUninitializeEE](../hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5d77-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e5d77-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="e5d77-105">Члены</span><span class="sxs-lookup"><span data-stu-id="e5d77-105">Members</span></span>  
  
|<span data-ttu-id="e5d77-106">Член</span><span class="sxs-lookup"><span data-stu-id="e5d77-106">Member</span></span>|<span data-ttu-id="e5d77-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e5d77-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="e5d77-108">Указывает режим деинициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e5d77-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="e5d77-109">Указывает режим отмены инициализации для выгрузки сборки.</span><span class="sxs-lookup"><span data-stu-id="e5d77-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e5d77-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e5d77-110">Requirements</span></span>  

 <span data-ttu-id="e5d77-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5d77-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5d77-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e5d77-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5d77-113">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5d77-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e5d77-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5d77-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5d77-115">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e5d77-115">See also</span></span>

- [<span data-ttu-id="e5d77-116">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="e5d77-116">Metadata Enumerations</span></span>](metadata-enumerations.md)

---
title: Перечисление COINITIEE
ms.date: 03/30/2017
api_name:
- COINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COINITIEE
helpviewer_keywords:
- COINITIEE enumeration [.NET Framework metadata]
ms.assetid: 64264238-3b68-4bac-a887-36b552426a6c
topic_type:
- apiref
ms.openlocfilehash: f4d1c2f105abb64bf196d0dd8371c2788c97336e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005912"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="473e8-102">Перечисление COINITIEE</span><span class="sxs-lookup"><span data-stu-id="473e8-102">COINITIEE Enumeration</span></span>
<span data-ttu-id="473e8-103">Указывает константы, используемые [CoInitialize](../hosting/coinitializeee-function.md) при инициализации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="473e8-103">Specifies constants used by [CoInitializeEE](../hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="473e8-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="473e8-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="473e8-105">Участники</span><span class="sxs-lookup"><span data-stu-id="473e8-105">Members</span></span>  
  
|<span data-ttu-id="473e8-106">Член</span><span class="sxs-lookup"><span data-stu-id="473e8-106">Member</span></span>|<span data-ttu-id="473e8-107">Описание</span><span class="sxs-lookup"><span data-stu-id="473e8-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="473e8-108">Режим инициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="473e8-108">Default initialization mode.</span></span> <span data-ttu-id="473e8-109">Это Инициализирует среду выполнения и создает значение по умолчанию <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="473e8-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="473e8-110">Инициализирует для запуска управляемой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="473e8-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="473e8-111">Инициализирует для запуска управляемого EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="473e8-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="473e8-112">При этом инициализируется среда выполнения, но не создается значение по умолчанию <xref:System.AppDomain> , которое создается после ввода основной подпрограммы exe-файла.</span><span class="sxs-lookup"><span data-stu-id="473e8-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="473e8-113">Требования</span><span class="sxs-lookup"><span data-stu-id="473e8-113">Requirements</span></span>  
 <span data-ttu-id="473e8-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="473e8-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="473e8-115">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="473e8-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="473e8-116">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="473e8-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="473e8-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="473e8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="473e8-118">См. также статью</span><span class="sxs-lookup"><span data-stu-id="473e8-118">See also</span></span>

- [<span data-ttu-id="473e8-119">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="473e8-119">Metadata Enumerations</span></span>](metadata-enumerations.md)

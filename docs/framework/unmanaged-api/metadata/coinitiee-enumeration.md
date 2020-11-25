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
ms.openlocfilehash: 673450bb8209abede15e3cb65dd764b418073bc2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724199"
---
# <a name="coinitiee-enumeration"></a><span data-ttu-id="ff6bf-102">Перечисление COINITIEE</span><span class="sxs-lookup"><span data-stu-id="ff6bf-102">COINITIEE Enumeration</span></span>

<span data-ttu-id="ff6bf-103">Указывает константы, используемые [CoInitialize](../hosting/coinitializeee-function.md) при инициализации среды CLR.</span><span class="sxs-lookup"><span data-stu-id="ff6bf-103">Specifies constants used by [CoInitializeEE](../hosting/coinitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff6bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ff6bf-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOINITEE {  
   COINITEE_DEFAULT = 0x0,  
   COINITEE_DLL     = 0x1,  
   COINITEE_MAIN    = 0x2  
} COINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="ff6bf-105">Члены</span><span class="sxs-lookup"><span data-stu-id="ff6bf-105">Members</span></span>  
  
|<span data-ttu-id="ff6bf-106">Член</span><span class="sxs-lookup"><span data-stu-id="ff6bf-106">Member</span></span>|<span data-ttu-id="ff6bf-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ff6bf-107">Description</span></span>|  
|------------|-----------------|  
|`COINITEE_DEFAULT`|<span data-ttu-id="ff6bf-108">Режим инициализации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ff6bf-108">Default initialization mode.</span></span> <span data-ttu-id="ff6bf-109">Это Инициализирует среду выполнения и создает значение по умолчанию <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="ff6bf-109">This initializes the runtime and creates the default <xref:System.AppDomain>.</span></span>|  
|`COINITEE_DLL`|<span data-ttu-id="ff6bf-110">Инициализирует для запуска управляемой библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="ff6bf-110">Initializes to run a managed DLL.</span></span>|  
|`COINITEE_MAIN`|<span data-ttu-id="ff6bf-111">Инициализирует для запуска управляемого EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="ff6bf-111">Initializes to run a managed EXE.</span></span> <span data-ttu-id="ff6bf-112">При этом инициализируется среда выполнения, но не создается значение по умолчанию <xref:System.AppDomain> , которое создается после ввода основной подпрограммы exe-файла.</span><span class="sxs-lookup"><span data-stu-id="ff6bf-112">This initializes the runtime but does not create the default <xref:System.AppDomain>, which is created after entering the main routine of the EXE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ff6bf-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ff6bf-113">Requirements</span></span>  

 <span data-ttu-id="ff6bf-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff6bf-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff6bf-115">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ff6bf-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ff6bf-116">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ff6bf-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ff6bf-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff6bf-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff6bf-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ff6bf-118">See also</span></span>

- [<span data-ttu-id="ff6bf-119">Перечисления метаданных</span><span class="sxs-lookup"><span data-stu-id="ff6bf-119">Metadata Enumerations</span></span>](metadata-enumerations.md)

---
title: Метод ICeeGen::GetSectionCreate
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
ms.openlocfilehash: 4ef3992d840f539ca07c411c2d740fa32b14edbc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722951"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="e6df5-102">Метод ICeeGen::GetSectionCreate</span><span class="sxs-lookup"><span data-stu-id="e6df5-102">ICeeGen::GetSectionCreate Method</span></span>

<span data-ttu-id="e6df5-103">Создает и получает раздел кода, используя указанные значения имени и флага.</span><span class="sxs-lookup"><span data-stu-id="e6df5-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="e6df5-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="e6df5-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6df5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e6df5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6df5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e6df5-106">Parameters</span></span>  

 `name`  
 <span data-ttu-id="e6df5-107">окне Указатель на строку, указывающую имя создаваемого раздела.</span><span class="sxs-lookup"><span data-stu-id="e6df5-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="e6df5-108">окне Флаги, указывающие параметры.</span><span class="sxs-lookup"><span data-stu-id="e6df5-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="e6df5-109">заполняет Указатель на только что созданный раздел кода.</span><span class="sxs-lookup"><span data-stu-id="e6df5-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6df5-110">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e6df5-110">Remarks</span></span>  

 <span data-ttu-id="e6df5-111">Вызывайте `GetSectionCreate` только при наличии особых требований к разделам, которые не обрабатываются другими методами.</span><span class="sxs-lookup"><span data-stu-id="e6df5-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6df5-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e6df5-112">Requirements</span></span>  

 <span data-ttu-id="e6df5-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6df5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6df5-114">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e6df5-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e6df5-115">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e6df5-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e6df5-116">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6df5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6df5-117">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e6df5-117">See also</span></span>

- [<span data-ttu-id="e6df5-118">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="e6df5-118">ICeeGen Interface</span></span>](iceegen-interface.md)

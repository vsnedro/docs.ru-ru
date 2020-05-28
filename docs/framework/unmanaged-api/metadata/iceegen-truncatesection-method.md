---
title: Метод ICeeGen::TruncateSection
ms.date: 03/30/2017
api_name:
- ICeeGen.TruncateSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type:
- apiref
ms.openlocfilehash: 387f5f01f2d2589c0b34e50b69398e1feb0e77e0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008252"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="097d3-102">Метод ICeeGen::TruncateSection</span><span class="sxs-lookup"><span data-stu-id="097d3-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="097d3-103">Усекает указанный раздел кода на заданную длину.</span><span class="sxs-lookup"><span data-stu-id="097d3-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="097d3-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="097d3-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="097d3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="097d3-105">Syntax</span></span>  
  
```cpp  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="097d3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="097d3-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="097d3-107">окне Раздел для усечения.</span><span class="sxs-lookup"><span data-stu-id="097d3-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="097d3-108">окне Длина усечения раздела в байтах.</span><span class="sxs-lookup"><span data-stu-id="097d3-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="097d3-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="097d3-109">Remarks</span></span>  
 <span data-ttu-id="097d3-110">Вызывайте `TruncateSection` только при наличии особых требований к разделам, которые не обрабатываются другими методами.</span><span class="sxs-lookup"><span data-stu-id="097d3-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="097d3-111">Требования</span><span class="sxs-lookup"><span data-stu-id="097d3-111">Requirements</span></span>  
 <span data-ttu-id="097d3-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="097d3-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="097d3-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="097d3-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="097d3-114">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="097d3-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="097d3-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="097d3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="097d3-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="097d3-116">See also</span></span>

- [<span data-ttu-id="097d3-117">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="097d3-117">ICeeGen Interface</span></span>](iceegen-interface.md)

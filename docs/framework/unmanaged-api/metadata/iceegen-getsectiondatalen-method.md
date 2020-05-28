---
title: Метод ICeeGen::GetSectionDataLen
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionDataLen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type:
- apiref
ms.openlocfilehash: 1855c73849c35bf709b0af261a88e6cd7a40abfb
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008304"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="57fe0-102">Метод ICeeGen::GetSectionDataLen</span><span class="sxs-lookup"><span data-stu-id="57fe0-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="57fe0-103">Возвращает длину указанного раздела.</span><span class="sxs-lookup"><span data-stu-id="57fe0-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="57fe0-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="57fe0-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57fe0-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="57fe0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57fe0-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="57fe0-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="57fe0-107">окне Раздел данных, длина которого будет получена.</span><span class="sxs-lookup"><span data-stu-id="57fe0-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="57fe0-108">заполняет Возвращаемая длина указанного раздела.</span><span class="sxs-lookup"><span data-stu-id="57fe0-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="57fe0-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="57fe0-109">Remarks</span></span>  
 <span data-ttu-id="57fe0-110">Вызывайте `GetSectionDataLen` только при наличии особых требований к разделам, которые не обрабатываются другими методами.</span><span class="sxs-lookup"><span data-stu-id="57fe0-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57fe0-111">Требования</span><span class="sxs-lookup"><span data-stu-id="57fe0-111">Requirements</span></span>  
 <span data-ttu-id="57fe0-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57fe0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57fe0-113">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="57fe0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="57fe0-114">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="57fe0-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="57fe0-115">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57fe0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57fe0-116">См. также статью</span><span class="sxs-lookup"><span data-stu-id="57fe0-116">See also</span></span>

- [<span data-ttu-id="57fe0-117">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="57fe0-117">ICeeGen Interface</span></span>](iceegen-interface.md)

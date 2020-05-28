---
title: Метод ICeeGen::GetSectionBlock
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionBlock
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionBlock
helpviewer_keywords:
- GetSectionBlock method [.NET Framework metadata]
- ICeeGen::GetSectionBlock method [.NET Framework metadata]
ms.assetid: 05c78aaf-5bbd-497e-9ae2-55f4fae0c5fb
topic_type:
- apiref
ms.openlocfilehash: ed534890fc90d3b8543a1166c85903f10163f0a8
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008336"
---
# <a name="iceegengetsectionblock-method"></a><span data-ttu-id="a2b76-102">Метод ICeeGen::GetSectionBlock</span><span class="sxs-lookup"><span data-stu-id="a2b76-102">ICeeGen::GetSectionBlock Method</span></span>
<span data-ttu-id="a2b76-103">Возвращает блок базы кода.</span><span class="sxs-lookup"><span data-stu-id="a2b76-103">Gets a section block of the code base.</span></span>  
  
 <span data-ttu-id="a2b76-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="a2b76-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2b76-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a2b76-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionBlock (  
    [in]  HCEESECTION    section,
    [in]  ULONG          len,  
    [in]  ULONG          align     = 1,  
    [out] void           **ppBytes = 0  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="a2b76-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="a2b76-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="a2b76-107">окне Раздел, из которого извлекается блок базы кода.</span><span class="sxs-lookup"><span data-stu-id="a2b76-107">[in] The section from which to retrieve a block of the code base.</span></span>  
  
 `len`  
 <span data-ttu-id="a2b76-108">окне Длина извлекаемого блока.</span><span class="sxs-lookup"><span data-stu-id="a2b76-108">[in] The length of the block to be retrieved.</span></span>  
  
 `align`  
 <span data-ttu-id="a2b76-109">окне Байт относительно начала раздела, с которым будет выравняться первый байт блока.</span><span class="sxs-lookup"><span data-stu-id="a2b76-109">[in] The byte, relative to the beginning of the section, with which to align the first byte of the block.</span></span> <span data-ttu-id="a2b76-110">Это расположение блока в разделе.</span><span class="sxs-lookup"><span data-stu-id="a2b76-110">This is the position of the block within the section.</span></span>  
  
 `ppBytes`  
 <span data-ttu-id="a2b76-111">заполняет Указатель на расположение, которое получает адрес полученного блока.</span><span class="sxs-lookup"><span data-stu-id="a2b76-111">[out] A pointer to a location that receives the address of the retrieved block.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2b76-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="a2b76-112">Remarks</span></span>  
 <span data-ttu-id="a2b76-113">Вызывайте `GetSectionBlock` только при наличии особых требований к разделам, которые не обрабатываются другими методами.</span><span class="sxs-lookup"><span data-stu-id="a2b76-113">Call `GetSectionBlock` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2b76-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a2b76-114">Requirements</span></span>  
 <span data-ttu-id="a2b76-115">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2b76-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2b76-116">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="a2b76-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a2b76-117">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a2b76-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a2b76-118">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2b76-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b76-119">См. также статью</span><span class="sxs-lookup"><span data-stu-id="a2b76-119">See also</span></span>

- [<span data-ttu-id="a2b76-120">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="a2b76-120">ICeeGen Interface</span></span>](iceegen-interface.md)

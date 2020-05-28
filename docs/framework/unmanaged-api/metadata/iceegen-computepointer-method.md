---
title: Метод ICeeGen::ComputePointer
ms.date: 03/30/2017
api_name:
- ICeeGen.ComputePointer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::ComputePointer
helpviewer_keywords:
- ICeeGen::ComputePointer method [.NET Framework metadata]
- ComputePointer method [.NET Framework metadata]
ms.assetid: b6b95c04-0f2c-4fcc-a8bc-3b1dcbdba731
topic_type:
- apiref
ms.openlocfilehash: 206dcd3a0a82da9b6211c8c2045e4e9d3d991973
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008876"
---
# <a name="iceegencomputepointer-method"></a><span data-ttu-id="04ac7-102">Метод ICeeGen::ComputePointer</span><span class="sxs-lookup"><span data-stu-id="04ac7-102">ICeeGen::ComputePointer Method</span></span>
<span data-ttu-id="04ac7-103">Определяет буфер для указанного раздела кода.</span><span class="sxs-lookup"><span data-stu-id="04ac7-103">Determines the buffer for the specified code section.</span></span>  
  
 <span data-ttu-id="04ac7-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="04ac7-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04ac7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="04ac7-105">Syntax</span></span>  
  
```cpp  
HRESULT ComputePointer (  
    [in]  HCEESECTION  section,  
    [in]  ULONG        RVA,
    [out] UCHAR        **lpBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04ac7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="04ac7-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="04ac7-107">окне Раздел кода, для которого возвращается буфер.</span><span class="sxs-lookup"><span data-stu-id="04ac7-107">[in] The code section for which to return a buffer.</span></span>  
  
 `RVA`  
 <span data-ttu-id="04ac7-108">окне Относительный виртуальный адрес метода, для которого необходимо получить указатель.</span><span class="sxs-lookup"><span data-stu-id="04ac7-108">[in] The relative virtual address of the method for which to get a pointer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="04ac7-109">заполняет Указатель на возвращаемый буфер.</span><span class="sxs-lookup"><span data-stu-id="04ac7-109">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04ac7-110">Требования</span><span class="sxs-lookup"><span data-stu-id="04ac7-110">Requirements</span></span>  
 <span data-ttu-id="04ac7-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04ac7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04ac7-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="04ac7-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="04ac7-113">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="04ac7-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="04ac7-114">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04ac7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04ac7-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="04ac7-115">See also</span></span>

- [<span data-ttu-id="04ac7-116">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="04ac7-116">ICeeGen Interface</span></span>](iceegen-interface.md)

---
title: Метод ICeeGen::EmitString
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
ms.openlocfilehash: b9c907868df31da8d995c6a6b86db258d395335d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715450"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="e9171-102">Метод ICeeGen::EmitString</span><span class="sxs-lookup"><span data-stu-id="e9171-102">ICeeGen::EmitString Method</span></span>

<span data-ttu-id="e9171-103">Порождает указанную строку в базу кода.</span><span class="sxs-lookup"><span data-stu-id="e9171-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="e9171-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="e9171-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9171-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9171-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9171-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9171-106">Parameters</span></span>  

 `lpString`  
 <span data-ttu-id="e9171-107">окне Строка для выдачи.</span><span class="sxs-lookup"><span data-stu-id="e9171-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="e9171-108">заполняет Относительный виртуальный адрес порожденной строки.</span><span class="sxs-lookup"><span data-stu-id="e9171-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9171-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e9171-109">Requirements</span></span>  

 <span data-ttu-id="e9171-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9171-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9171-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="e9171-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9171-112">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9171-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e9171-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9171-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9171-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e9171-114">See also</span></span>

- [<span data-ttu-id="e9171-115">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="e9171-115">ICeeGen Interface</span></span>](iceegen-interface.md)

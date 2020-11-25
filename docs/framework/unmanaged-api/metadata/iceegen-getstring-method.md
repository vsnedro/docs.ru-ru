---
title: Метод ICeeGen::GetString
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
ms.openlocfilehash: 9d14ec33128596a148ca3509a49c8c97fafe82d6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723107"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="5ebaf-102">Метод ICeeGen::GetString</span><span class="sxs-lookup"><span data-stu-id="5ebaf-102">ICeeGen::GetString Method</span></span>

<span data-ttu-id="5ebaf-103">Возвращает строку, хранящуюся по указанному относительному виртуальному адресу.</span><span class="sxs-lookup"><span data-stu-id="5ebaf-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="5ebaf-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="5ebaf-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ebaf-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ebaf-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ebaf-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ebaf-106">Parameters</span></span>  

 `RVA`  
 <span data-ttu-id="5ebaf-107">окне Относительный виртуальный адрес возвращаемой строки.</span><span class="sxs-lookup"><span data-stu-id="5ebaf-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="5ebaf-108">заполняет Возвращаемая строка.</span><span class="sxs-lookup"><span data-stu-id="5ebaf-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ebaf-109">Требования</span><span class="sxs-lookup"><span data-stu-id="5ebaf-109">Requirements</span></span>  

 <span data-ttu-id="5ebaf-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ebaf-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ebaf-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="5ebaf-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ebaf-112">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ebaf-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ebaf-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ebaf-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ebaf-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5ebaf-114">See also</span></span>

- [<span data-ttu-id="5ebaf-115">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="5ebaf-115">ICeeGen Interface</span></span>](iceegen-interface.md)

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
ms.openlocfilehash: b7b15261d825c1bd5f217c4cecd82ed36a716d0e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008265"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="270b6-102">Метод ICeeGen::GetString</span><span class="sxs-lookup"><span data-stu-id="270b6-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="270b6-103">Возвращает строку, хранящуюся по указанному относительному виртуальному адресу.</span><span class="sxs-lookup"><span data-stu-id="270b6-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="270b6-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="270b6-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="270b6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="270b6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="270b6-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="270b6-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="270b6-107">окне Относительный виртуальный адрес возвращаемой строки.</span><span class="sxs-lookup"><span data-stu-id="270b6-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="270b6-108">заполняет Возвращаемая строка.</span><span class="sxs-lookup"><span data-stu-id="270b6-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="270b6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="270b6-109">Requirements</span></span>  
 <span data-ttu-id="270b6-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="270b6-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="270b6-111">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="270b6-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="270b6-112">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="270b6-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="270b6-113">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="270b6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="270b6-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="270b6-114">See also</span></span>

- [<span data-ttu-id="270b6-115">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="270b6-115">ICeeGen Interface</span></span>](iceegen-interface.md)

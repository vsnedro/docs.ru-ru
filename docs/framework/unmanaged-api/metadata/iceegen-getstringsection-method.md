---
title: Метод ICeeGen::GetStringSection
ms.date: 03/30/2017
api_name:
- ICeeGen.GetStringSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type:
- apiref
ms.openlocfilehash: dbbfa77ee76770bcf1d662bc5ae179909eaf3b25
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008291"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="b326c-102">Метод ICeeGen::GetStringSection</span><span class="sxs-lookup"><span data-stu-id="b326c-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="b326c-103">Возвращает строковое представление раздела кода, на который ссылается указанный маркер.</span><span class="sxs-lookup"><span data-stu-id="b326c-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="b326c-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="b326c-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b326c-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b326c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b326c-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b326c-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="b326c-107">[вход, выход] Маркер раздела кода.</span><span class="sxs-lookup"><span data-stu-id="b326c-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b326c-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b326c-108">Requirements</span></span>  
 <span data-ttu-id="b326c-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b326c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b326c-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="b326c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b326c-111">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b326c-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b326c-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b326c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b326c-113">См. также статью</span><span class="sxs-lookup"><span data-stu-id="b326c-113">See also</span></span>

- [<span data-ttu-id="b326c-114">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="b326c-114">ICeeGen Interface</span></span>](iceegen-interface.md)

---
title: Метод ICeeGen::GetIlSection
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
ms.openlocfilehash: c179d5e1ca976d8f425e7c408ceb663cba64f641
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715346"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="f62e1-102">Метод ICeeGen::GetIlSection</span><span class="sxs-lookup"><span data-stu-id="f62e1-102">ICeeGen::GetIlSection Method</span></span>

<span data-ttu-id="f62e1-103">Возвращает раздел базы кода промежуточного языка, на который ссылается указанный обработчик.</span><span class="sxs-lookup"><span data-stu-id="f62e1-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="f62e1-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="f62e1-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f62e1-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f62e1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f62e1-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="f62e1-106">Parameters</span></span>  

 `section`  
 <span data-ttu-id="f62e1-107">окне Описатель для получаемого раздела.</span><span class="sxs-lookup"><span data-stu-id="f62e1-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f62e1-108">Требования</span><span class="sxs-lookup"><span data-stu-id="f62e1-108">Requirements</span></span>  

 <span data-ttu-id="f62e1-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f62e1-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f62e1-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="f62e1-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f62e1-111">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f62e1-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f62e1-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f62e1-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f62e1-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f62e1-113">See also</span></span>

- [<span data-ttu-id="f62e1-114">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="f62e1-114">ICeeGen Interface</span></span>](iceegen-interface.md)

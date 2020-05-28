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
ms.openlocfilehash: 05f39befa8966046cd71db82da37c44f20992cff
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008811"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="3e39b-102">Метод ICeeGen::GetIlSection</span><span class="sxs-lookup"><span data-stu-id="3e39b-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="3e39b-103">Возвращает раздел базы кода промежуточного языка, на который ссылается указанный обработчик.</span><span class="sxs-lookup"><span data-stu-id="3e39b-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="3e39b-104">Этот метод устарел и не должен использоваться.</span><span class="sxs-lookup"><span data-stu-id="3e39b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e39b-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e39b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e39b-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3e39b-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="3e39b-107">окне Описатель для получаемого раздела.</span><span class="sxs-lookup"><span data-stu-id="3e39b-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e39b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="3e39b-108">Requirements</span></span>  
 <span data-ttu-id="3e39b-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e39b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e39b-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="3e39b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3e39b-111">**Библиотека:** Используется в качестве ресурса в MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3e39b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3e39b-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e39b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e39b-113">См. также статью</span><span class="sxs-lookup"><span data-stu-id="3e39b-113">See also</span></span>

- [<span data-ttu-id="3e39b-114">Интерфейс ICeeGen</span><span class="sxs-lookup"><span data-stu-id="3e39b-114">ICeeGen Interface</span></span>](iceegen-interface.md)

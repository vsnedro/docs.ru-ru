---
title: Метод IAssemblyName::GetProperty
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetProperty
helpviewer_keywords:
- IAssemblyName::GetProperty method [.NET Framework fusion]
- GetProperty method [.NET Framework fusion]
ms.assetid: e59fda62-77d5-4e37-89cb-ce7ae4627975
topic_type:
- apiref
ms.openlocfilehash: 3a6f19d9fc90972e767625fadf30cc4af50d9017
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727891"
---
# <a name="iassemblynamegetproperty-method"></a><span data-ttu-id="6eaee-102">Метод IAssemblyName::GetProperty</span><span class="sxs-lookup"><span data-stu-id="6eaee-102">IAssemblyName::GetProperty Method</span></span>

<span data-ttu-id="6eaee-103">Возвращает указатель на свойство, на которое ссылается указанный идентификатор свойства.</span><span class="sxs-lookup"><span data-stu-id="6eaee-103">Gets a pointer to the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6eaee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6eaee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProperty (  
    [in]      DWORD    PropertyId,  
    [out]     LPVOID   pvProperty,  
    [in, out] LPDWORD  pcbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6eaee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6eaee-105">Parameters</span></span>  

 `PropertyId`  
 <span data-ttu-id="6eaee-106">окне Уникальный идентификатор запрошенного свойства.</span><span class="sxs-lookup"><span data-stu-id="6eaee-106">[in] The unique identifier for the requested property.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="6eaee-107">заполняет Возвращаемые данные свойства.</span><span class="sxs-lookup"><span data-stu-id="6eaee-107">[out] The returned property data.</span></span>  
  
 `pcbProperty`  
 <span data-ttu-id="6eaee-108">[вход, выход] Размер (в байтах) `pvProperty` .</span><span class="sxs-lookup"><span data-stu-id="6eaee-108">[in, out] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6eaee-109">Требования</span><span class="sxs-lookup"><span data-stu-id="6eaee-109">Requirements</span></span>  

 <span data-ttu-id="6eaee-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6eaee-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6eaee-111">**Заголовок:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="6eaee-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="6eaee-112">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6eaee-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eaee-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6eaee-113">See also</span></span>

- [<span data-ttu-id="6eaee-114">Интерфейс IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="6eaee-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)

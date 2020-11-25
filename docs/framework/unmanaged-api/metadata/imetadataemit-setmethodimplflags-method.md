---
title: Метод IMetaDataEmit::SetMethodImplFlags
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetMethodImplFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetMethodImplFlags
helpviewer_keywords:
- IMetaDataEmit::SetMethodImplFlags method [.NET Framework metadata]
- SetMethodImpFlags method [.NET Framework metadata]
ms.assetid: 4bc82d9b-9544-4be3-ba51-a2d4d806158a
topic_type:
- apiref
ms.openlocfilehash: 486d545413337f6696bd9f21c516466fc3747256
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730361"
---
# <a name="imetadataemitsetmethodimplflags-method"></a><span data-ttu-id="c2e88-102">Метод IMetaDataEmit::SetMethodImplFlags</span><span class="sxs-lookup"><span data-stu-id="c2e88-102">IMetaDataEmit::SetMethodImplFlags Method</span></span>

<span data-ttu-id="c2e88-103">Задает или обновляет сигнатуру метаданных реализации унаследованного метода, на которую ссылается указанный токен.</span><span class="sxs-lookup"><span data-stu-id="c2e88-103">Sets or updates the metadata signature of the inherited method implementation that is referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2e88-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2e88-104">Syntax</span></span>  
  
```cpp  
HRESULT SetMethodImplFlags (
    [in]  mdMethodDef   md,
    [in]  DWORD         dwImplFlags
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2e88-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2e88-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="c2e88-106">окне Токен для изменяемого метода.</span><span class="sxs-lookup"><span data-stu-id="c2e88-106">[in] The token for the method to be changed.</span></span>  
  
 `dwImplFlags`  
 <span data-ttu-id="c2e88-107">окне Сочетание значений перечисления [кормесодимпл](cormethodimpl-enumeration.md) , определяющих функции реализации метода.</span><span class="sxs-lookup"><span data-stu-id="c2e88-107">[in] A combination of the values of the [CorMethodImpl](cormethodimpl-enumeration.md) enumeration that specifies the method implementation features.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2e88-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c2e88-108">Requirements</span></span>  

 <span data-ttu-id="c2e88-109">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2e88-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2e88-110">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="c2e88-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2e88-111">**Библиотека:** Используется в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c2e88-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c2e88-112">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2e88-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2e88-113">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c2e88-113">See also</span></span>

- [<span data-ttu-id="c2e88-114">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="c2e88-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c2e88-115">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="c2e88-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

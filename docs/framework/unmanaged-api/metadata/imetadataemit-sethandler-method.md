---
title: Метод IMetaDataEmit::SetHandler
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetHandler
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetHandler
helpviewer_keywords:
- IMetaDataEmit::SetHandler method [.NET Framework metadata]
- SetHandler method [.NET Framework metadata]
ms.assetid: c6c1aaaf-e2cd-407c-b73e-fbe6ffd83bb3
topic_type:
- apiref
ms.openlocfilehash: 4fa227d18b8cb10936d93fda9bcaf413ce63ca3b
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003958"
---
# <a name="imetadataemitsethandler-method"></a><span data-ttu-id="1b50d-102">Метод IMetaDataEmit::SetHandler</span><span class="sxs-lookup"><span data-stu-id="1b50d-102">IMetaDataEmit::SetHandler Method</span></span>
<span data-ttu-id="1b50d-103">Задает метод, на который ссылается указанный `IUnknown` указатель, в качестве обратного вызова уведомления для повторного сопоставления токена.</span><span class="sxs-lookup"><span data-stu-id="1b50d-103">Sets the method referenced by the specified `IUnknown` pointer as a notification callback for token remaps.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b50d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1b50d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetHandler (
    [in]  IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b50d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="1b50d-105">Parameters</span></span>  
 `pUnk`  
 <span data-ttu-id="1b50d-106">окне Регистрируемый обработчик.</span><span class="sxs-lookup"><span data-stu-id="1b50d-106">[in] The handler to register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b50d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="1b50d-107">Remarks</span></span>  
 <span data-ttu-id="1b50d-108">Обработчик метаданных отправляет уведомление с помощью метода, предоставляемого `SetHandler` , компиляторам, которые не создают записи оптимизированным образом и хотели бы оптимизировать сохраненные записи.</span><span class="sxs-lookup"><span data-stu-id="1b50d-108">The metadata engine sends notification by using the method that is provided by `SetHandler`, to compilers that do not generate records in an optimized way and that would like to optimize saved records.</span></span>  
  
 <span data-ttu-id="1b50d-109">Если метод обратного вызова не предоставляется через `SetHandler` , то для сохранения не будет выполняться оптимизация, за исключением случаев, когда для каждой области были объединены несколько областей импорта с использованием `IMapToken` On MERGE.</span><span class="sxs-lookup"><span data-stu-id="1b50d-109">If the callback method is not provided through `SetHandler`, no optimization will be performed on save except where several import scopes have been merged using `IMapToken` on merge for each scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b50d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="1b50d-110">Requirements</span></span>  
 <span data-ttu-id="1b50d-111">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b50d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b50d-112">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="1b50d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1b50d-113">**Библиотека:** Используется в качестве ресурса в MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1b50d-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1b50d-114">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b50d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b50d-115">См. также статью</span><span class="sxs-lookup"><span data-stu-id="1b50d-115">See also</span></span>

- [<span data-ttu-id="1b50d-116">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="1b50d-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="1b50d-117">Интерфейс IMetaDataEmit2</span><span class="sxs-lookup"><span data-stu-id="1b50d-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)

---
title: Интерфейс IMetaDataDispenserEx
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
ms.openlocfilehash: 60d321c1a87a5da433437c9d4587fa9f8947acf4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95713383"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="2a820-102">Интерфейс IMetaDataDispenserEx</span><span class="sxs-lookup"><span data-stu-id="2a820-102">IMetaDataDispenserEx Interface</span></span>

<span data-ttu-id="2a820-103">Расширяет интерфейс [интерфейса IMetaDataDispenser](imetadatadispenser-interface.md) , чтобы предоставить возможность контролировать работу API метаданных в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="2a820-103">Extends the [IMetaDataDispenser Interface](imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2a820-104">Методы</span><span class="sxs-lookup"><span data-stu-id="2a820-104">Methods</span></span>  
  
|<span data-ttu-id="2a820-105">Метод</span><span class="sxs-lookup"><span data-stu-id="2a820-105">Method</span></span>|<span data-ttu-id="2a820-106">Описание</span><span class="sxs-lookup"><span data-stu-id="2a820-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2a820-107">Метод FindAssembly</span><span class="sxs-lookup"><span data-stu-id="2a820-107">FindAssembly Method</span></span>](imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="2a820-108">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="2a820-108">This method is not implemented.</span></span> <span data-ttu-id="2a820-109">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="2a820-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="2a820-110">Метод FindAssemblyModule</span><span class="sxs-lookup"><span data-stu-id="2a820-110">FindAssemblyModule Method</span></span>](imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="2a820-111">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="2a820-111">This method is not implemented.</span></span> <span data-ttu-id="2a820-112">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="2a820-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="2a820-113">Метод GetCORSystemDirectory</span><span class="sxs-lookup"><span data-stu-id="2a820-113">GetCORSystemDirectory Method</span></span>](imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="2a820-114">Возвращает каталог, содержащий текущую среду CLR.</span><span class="sxs-lookup"><span data-stu-id="2a820-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="2a820-115">Этот метод поддерживается только для использования необработанными отладчиками.</span><span class="sxs-lookup"><span data-stu-id="2a820-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="2a820-116">Если вызывается из другого компонента, он возвратит E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="2a820-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="2a820-117">Метод GetOption</span><span class="sxs-lookup"><span data-stu-id="2a820-117">GetOption Method</span></span>](imetadatadispenserex-getoption-method.md)|<span data-ttu-id="2a820-118">Возвращает значение указанного параметра для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="2a820-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="2a820-119">Параметр определяет, как обрабатываются вызовы к текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="2a820-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="2a820-120">Метод OpenScopeOnITypeInfo</span><span class="sxs-lookup"><span data-stu-id="2a820-120">OpenScopeOnITypeInfo Method</span></span>](imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="2a820-121">Этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="2a820-121">This method is not implemented.</span></span> <span data-ttu-id="2a820-122">При вызове возвращается E_NOTIMPL.</span><span class="sxs-lookup"><span data-stu-id="2a820-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="2a820-123">Метод SetOption</span><span class="sxs-lookup"><span data-stu-id="2a820-123">SetOption Method</span></span>](imetadatadispenserex-setoption-method.md)|<span data-ttu-id="2a820-124">Задает для указанного параметра заданное значение для текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="2a820-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="2a820-125">Параметр определяет, как обрабатываются вызовы к текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="2a820-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a820-126">Требования</span><span class="sxs-lookup"><span data-stu-id="2a820-126">Requirements</span></span>  

 <span data-ttu-id="2a820-127">**Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a820-127">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a820-128">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="2a820-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a820-129">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a820-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a820-130">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a820-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a820-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2a820-131">See also</span></span>

- [<span data-ttu-id="2a820-132">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="2a820-132">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="2a820-133">Интерфейс IMetaDataDispenser</span><span class="sxs-lookup"><span data-stu-id="2a820-133">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="2a820-134">Интерфейс IMetaDataEmit</span><span class="sxs-lookup"><span data-stu-id="2a820-134">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="2a820-135">Интерфейс IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="2a820-135">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)

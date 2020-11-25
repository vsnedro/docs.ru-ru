---
title: Интерфейс IMetaDataFilter
ms.date: 03/30/2017
api_name:
- IMetaDataFilter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter
helpviewer_keywords:
- IMetaDataFilter interface [.NET Framework metadata]
ms.assetid: ec0856ef-8c56-40ba-bf60-86e0ce8b337f
topic_type:
- apiref
ms.openlocfilehash: 2c22e45ca3d33b0a81ff0ecd90bf7574c45676bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701852"
---
# <a name="imetadatafilter-interface"></a><span data-ttu-id="ebd40-102">Интерфейс IMetaDataFilter</span><span class="sxs-lookup"><span data-stu-id="ebd40-102">IMetaDataFilter Interface</span></span>

<span data-ttu-id="ebd40-103">Предоставляет методы для пометки и фильтрации лексем метаданных во избежание повторения действий, которые уже были выполнены.</span><span class="sxs-lookup"><span data-stu-id="ebd40-103">Provides methods for marking and filtering metadata tokens to avoid repeating actions that have already been taken.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ebd40-104">Методы</span><span class="sxs-lookup"><span data-stu-id="ebd40-104">Methods</span></span>  
  
|<span data-ttu-id="ebd40-105">Метод</span><span class="sxs-lookup"><span data-stu-id="ebd40-105">Method</span></span>|<span data-ttu-id="ebd40-106">Описание</span><span class="sxs-lookup"><span data-stu-id="ebd40-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ebd40-107">Метод IsTokenMarked</span><span class="sxs-lookup"><span data-stu-id="ebd40-107">IsTokenMarked Method</span></span>](imetadatafilter-istokenmarked-method.md)|<span data-ttu-id="ebd40-108">Возвращает значение, указывающее, был ли обработан заданный маркер метаданных.</span><span class="sxs-lookup"><span data-stu-id="ebd40-108">Gets a value indicating whether the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="ebd40-109">Метод MarkToken</span><span class="sxs-lookup"><span data-stu-id="ebd40-109">MarkToken Method</span></span>](imetadatafilter-marktoken-method.md)|<span data-ttu-id="ebd40-110">Задает значение, указывающее, что указанный токен метаданных был обработан.</span><span class="sxs-lookup"><span data-stu-id="ebd40-110">Sets a value indicating that the specified metadata token has been processed.</span></span>|  
|[<span data-ttu-id="ebd40-111">Метод UnmarkAll</span><span class="sxs-lookup"><span data-stu-id="ebd40-111">UnmarkAll Method</span></span>](imetadatafilter-unmarkall-method.md)|<span data-ttu-id="ebd40-112">Удаляет метки обработки из всех токенов в текущей области метаданных.</span><span class="sxs-lookup"><span data-stu-id="ebd40-112">Removes the processing marks from all the tokens in the current metadata scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ebd40-113">Требования</span><span class="sxs-lookup"><span data-stu-id="ebd40-113">Requirements</span></span>  

 <span data-ttu-id="ebd40-114">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebd40-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebd40-115">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="ebd40-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ebd40-116">**Библиотека:** Используется в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ebd40-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ebd40-117">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebd40-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebd40-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ebd40-118">See also</span></span>

- [<span data-ttu-id="ebd40-119">Интерфейсы метаданных</span><span class="sxs-lookup"><span data-stu-id="ebd40-119">Metadata Interfaces</span></span>](metadata-interfaces.md)

---
title: Функция CoInitializeEE
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
ms.openlocfilehash: 707e182e62f4a7b7b813e6b288c6825b0d3d2eab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731759"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="6f612-102">Функция CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="6f612-102">CoInitializeEE Function</span></span>

<span data-ttu-id="6f612-103">Гарантирует, что подсистема выполнения среды CLR загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="6f612-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="6f612-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="6f612-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="6f612-105">Используйте вместо этого метод [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6f612-105">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f612-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6f612-106">Syntax</span></span>  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f612-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="6f612-107">Parameters</span></span>  

 `fFlags`  
 <span data-ttu-id="6f612-108">окне Одна из констант перечисления [коинитии](../metadata/coinitiee-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="6f612-108">[in] One of the [COINITIEE](../metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f612-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6f612-109">Return Value</span></span>  

 <span data-ttu-id="6f612-110">Этот метод возвращает стандартные коды ошибок COM, определенные в файле Winerror. h, и значения, приведенные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6f612-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="6f612-111">Код возврата</span><span class="sxs-lookup"><span data-stu-id="6f612-111">Return code</span></span>|<span data-ttu-id="6f612-112">Описание</span><span class="sxs-lookup"><span data-stu-id="6f612-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="6f612-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f612-113">S_OK</span></span>|<span data-ttu-id="6f612-114">Подсистема выполнения успешно загружена.</span><span class="sxs-lookup"><span data-stu-id="6f612-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="6f612-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6f612-115">S_FALSE</span></span>|<span data-ttu-id="6f612-116">Подсистема выполнения уже загружена.</span><span class="sxs-lookup"><span data-stu-id="6f612-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="6f612-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6f612-117">E_FAIL</span></span>|<span data-ttu-id="6f612-118">Не удалось загрузить подсистему выполнения.</span><span class="sxs-lookup"><span data-stu-id="6f612-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f612-119">Комментарии</span><span class="sxs-lookup"><span data-stu-id="6f612-119">Remarks</span></span>  

 <span data-ttu-id="6f612-120">Этот метод загружает подсистему выполнения, если он не был загружен ранее.</span><span class="sxs-lookup"><span data-stu-id="6f612-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f612-121">Требования</span><span class="sxs-lookup"><span data-stu-id="6f612-121">Requirements</span></span>  

 <span data-ttu-id="6f612-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f612-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f612-123">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="6f612-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6f612-124">**Библиотека:** Включается в качестве ресурса в MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6f612-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6f612-125">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f612-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f612-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6f612-126">See also</span></span>

- [<span data-ttu-id="6f612-127">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="6f612-127">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)

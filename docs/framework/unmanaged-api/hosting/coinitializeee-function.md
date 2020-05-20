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
ms.openlocfilehash: 57508a2df3a49c39d25347f2a3038442c37278da
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616766"
---
# <a name="coinitializeee-function"></a><span data-ttu-id="64be6-102">Функция CoInitializeEE</span><span class="sxs-lookup"><span data-stu-id="64be6-102">CoInitializeEE Function</span></span>
<span data-ttu-id="64be6-103">Гарантирует, что подсистема выполнения среды CLR загружается в процесс.</span><span class="sxs-lookup"><span data-stu-id="64be6-103">Ensures that the common language runtime execution engine is loaded into a process.</span></span> <span data-ttu-id="64be6-104">Эта функция является устаревшей в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="64be6-104">This function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="64be6-105">Используйте вместо этого метод [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .</span><span class="sxs-lookup"><span data-stu-id="64be6-105">Use the [ICLRRuntimeHost::Start](iclrruntimehost-start-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64be6-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64be6-106">Syntax</span></span>  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64be6-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="64be6-107">Parameters</span></span>  
 `fFlags`  
 <span data-ttu-id="64be6-108">окне Одна из констант перечисления [коинитии](../metadata/coinitiee-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="64be6-108">[in] One of the [COINITIEE](../metadata/coinitiee-enumeration.md) enumeration constants.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="64be6-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="64be6-109">Return Value</span></span>  
 <span data-ttu-id="64be6-110">Этот метод возвращает стандартные коды ошибок COM, определенные в файле Winerror. h, и значения, приведенные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="64be6-110">This method returns standard COM error codes as defined in Winerror.h, and the values in the following table.</span></span>  
  
|<span data-ttu-id="64be6-111">Код возврата</span><span class="sxs-lookup"><span data-stu-id="64be6-111">Return code</span></span>|<span data-ttu-id="64be6-112">Описание</span><span class="sxs-lookup"><span data-stu-id="64be6-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="64be6-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="64be6-113">S_OK</span></span>|<span data-ttu-id="64be6-114">Подсистема выполнения успешно загружена.</span><span class="sxs-lookup"><span data-stu-id="64be6-114">The execution engine was loaded successfully.</span></span>|  
|<span data-ttu-id="64be6-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="64be6-115">S_FALSE</span></span>|<span data-ttu-id="64be6-116">Подсистема выполнения уже загружена.</span><span class="sxs-lookup"><span data-stu-id="64be6-116">The execution engine is already loaded.</span></span>|  
|<span data-ttu-id="64be6-117">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="64be6-117">E_FAIL</span></span>|<span data-ttu-id="64be6-118">Не удалось загрузить подсистему выполнения.</span><span class="sxs-lookup"><span data-stu-id="64be6-118">The execution engine could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64be6-119">Комментарии</span><span class="sxs-lookup"><span data-stu-id="64be6-119">Remarks</span></span>  
 <span data-ttu-id="64be6-120">Этот метод загружает подсистему выполнения, если он не был загружен ранее.</span><span class="sxs-lookup"><span data-stu-id="64be6-120">This method loads the execution engine if it has not been previously loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64be6-121">Требования</span><span class="sxs-lookup"><span data-stu-id="64be6-121">Requirements</span></span>  
 <span data-ttu-id="64be6-122">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64be6-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64be6-123">**Заголовок:** COR. h</span><span class="sxs-lookup"><span data-stu-id="64be6-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64be6-124">**Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="64be6-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="64be6-125">**.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64be6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64be6-126">См. также статью</span><span class="sxs-lookup"><span data-stu-id="64be6-126">See also</span></span>

- [<span data-ttu-id="64be6-127">Глобальные статические функции метаданных</span><span class="sxs-lookup"><span data-stu-id="64be6-127">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)

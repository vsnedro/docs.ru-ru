---
title: Метод IValidator::FormatEventInfo
ms.date: 03/30/2017
api_name:
- IValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- FormatEventInfo
helpviewer_keywords:
- IValidator::FormatEventInfo method [.NET Framework hosting]
- FormatEventInfo method, IValidator interface [.NET Framework hosting]
ms.assetid: 4c0c7477-05ba-461b-b21b-cbfba95f1db1
topic_type:
- apiref
ms.openlocfilehash: 0c60631b5e034bc46d74412440d35d526359d043
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008577"
---
# <a name="ivalidatorformateventinfo-method"></a><span data-ttu-id="13b14-102">Метод IValidator::FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="13b14-102">IValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="13b14-103">Возвращает сообщение об ошибке, соответствующее указанной ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="13b14-103">Gets the error message corresponding to the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13b14-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="13b14-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo(  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13b14-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="13b14-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="13b14-106">окне Значение HRESULT, которое было передано обработчику ошибок проверки.</span><span class="sxs-lookup"><span data-stu-id="13b14-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="13b14-107">окне `VEContext`Экземпляр, содержащий контекстные сведения об ошибке проверки.</span><span class="sxs-lookup"><span data-stu-id="13b14-107">[in] A `VEContext` instance that contains context information about the validation error.</span></span>  
  
 `msg`  
 <span data-ttu-id="13b14-108">[вход, выход] Строка, содержащая возвращенное сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="13b14-108">[in, out] A string that contains the returned error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="13b14-109">окне Максимальная длина сообщения об ошибке.</span><span class="sxs-lookup"><span data-stu-id="13b14-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="13b14-110">окне Защищенный массив, содержащий дополнительные параметры, описывающие ошибку.</span><span class="sxs-lookup"><span data-stu-id="13b14-110">[in] A safe array that contains additional parameters describing the error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13b14-111">Требования</span><span class="sxs-lookup"><span data-stu-id="13b14-111">Requirements</span></span>  
 <span data-ttu-id="13b14-112">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13b14-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13b14-113">**Заголовок:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="13b14-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="13b14-114">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="13b14-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13b14-115">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13b14-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  

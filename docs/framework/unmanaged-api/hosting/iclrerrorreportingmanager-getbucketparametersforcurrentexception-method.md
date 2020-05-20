---
title: Метод ICLRErrorReportingManager::GetBucketParametersForCurrentException
ms.date: 03/30/2017
api_name:
- ICLRErrorReportingManager.GetBucketParametersForCurrentException
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException
helpviewer_keywords:
- ICLRErrorReportingManager::GetBucketParametersForCurrentException method [.NET Framework hosting]
- GetBucketParametersForCurrentException method [.NET Framework hosting]
ms.assetid: a13ec8a6-8e18-4acb-8054-77f5b1a0e0b9
topic_type:
- apiref
ms.openlocfilehash: 969d74933e908674225684a2e77d5c4804b86122
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615648"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="ca5fd-102">Метод ICLRErrorReportingManager::GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="ca5fd-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>
<span data-ttu-id="ca5fd-103">Возвращает контейнер Watson для текущего исключения в вызывающем потоке.</span><span class="sxs-lookup"><span data-stu-id="ca5fd-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="ca5fd-104">*Контейнер* — это коллекция данных об ошибках, которая связана с тем же дефектом кода.</span><span class="sxs-lookup"><span data-stu-id="ca5fd-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="ca5fd-105">*Watson* относится к набору технологий для сбора и анализа данных, связанных с исключением.</span><span class="sxs-lookup"><span data-stu-id="ca5fd-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca5fd-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ca5fd-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca5fd-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="ca5fd-107">Parameters</span></span>  
 `pParams`  
 <span data-ttu-id="ca5fd-108">заполняет Указатель на структуру [буккетпараметерс](bucketparameters-structure.md) , содержащую данные об ошибке для исключения.</span><span class="sxs-lookup"><span data-stu-id="ca5fd-108">[out] A pointer to a [BucketParameters](bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca5fd-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ca5fd-109">Requirements</span></span>  
 <span data-ttu-id="ca5fd-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca5fd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca5fd-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ca5fd-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ca5fd-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ca5fd-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ca5fd-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca5fd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca5fd-114">См. также статью</span><span class="sxs-lookup"><span data-stu-id="ca5fd-114">See also</span></span>

- [<span data-ttu-id="ca5fd-115">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="ca5fd-115">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)

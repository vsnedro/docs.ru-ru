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
ms.openlocfilehash: 33927cc0e3a3cdaad70d437f9dd5ca5dfdcdc46b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673567"
---
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a><span data-ttu-id="8fc71-102">Метод ICLRErrorReportingManager::GetBucketParametersForCurrentException</span><span class="sxs-lookup"><span data-stu-id="8fc71-102">ICLRErrorReportingManager::GetBucketParametersForCurrentException Method</span></span>

<span data-ttu-id="8fc71-103">Возвращает контейнер Watson для текущего исключения в вызывающем потоке.</span><span class="sxs-lookup"><span data-stu-id="8fc71-103">Gets the Watson bucket for the current exception on the calling thread.</span></span>  
  
 <span data-ttu-id="8fc71-104">*Контейнер* — это коллекция данных об ошибках, которая связана с тем же дефектом кода.</span><span class="sxs-lookup"><span data-stu-id="8fc71-104">A *bucket* is a collection of error data that is related to the same code defect.</span></span> <span data-ttu-id="8fc71-105">*Watson* относится к набору технологий для сбора и анализа данных, связанных с исключением.</span><span class="sxs-lookup"><span data-stu-id="8fc71-105">*Watson* refers to a set of technologies for collecting and analyzing data that is associated with an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fc71-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8fc71-106">Syntax</span></span>  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8fc71-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="8fc71-107">Parameters</span></span>  

 `pParams`  
 <span data-ttu-id="8fc71-108">заполняет Указатель на структуру [буккетпараметерс](bucketparameters-structure.md) , содержащую данные об ошибке для исключения.</span><span class="sxs-lookup"><span data-stu-id="8fc71-108">[out] A pointer to a [BucketParameters](bucketparameters-structure.md) structure that contains error data for the exception.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fc71-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8fc71-109">Requirements</span></span>  

 <span data-ttu-id="8fc71-110">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8fc71-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fc71-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8fc71-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8fc71-112">**Библиотека:** Включается в качестве ресурса в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8fc71-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8fc71-113">**.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fc71-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fc71-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="8fc71-114">See also</span></span>

- [<span data-ttu-id="8fc71-115">Интерфейс ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="8fc71-115">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)

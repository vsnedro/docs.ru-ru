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
# <a name="iclrerrorreportingmanagergetbucketparametersforcurrentexception-method"></a>Метод ICLRErrorReportingManager::GetBucketParametersForCurrentException
Возвращает контейнер Watson для текущего исключения в вызывающем потоке.  
  
 *Контейнер* — это коллекция данных об ошибках, которая связана с тем же дефектом кода. *Watson* относится к набору технологий для сбора и анализа данных, связанных с исключением.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetBucketParametersForCurrentException(  
    [out] BucketParameters *pParams  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pParams`  
 заполняет Указатель на структуру [буккетпараметерс](bucketparameters-structure.md) , содержащую данные об ошибке для исключения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md)

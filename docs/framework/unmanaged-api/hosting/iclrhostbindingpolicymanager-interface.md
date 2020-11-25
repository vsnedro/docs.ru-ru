---
title: Интерфейс ICLRHostBindingPolicyManager
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
ms.openlocfilehash: 49d1ee4dd0965d4ae5b54b53208809cfbdf7e718
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725638"
---
# <a name="iclrhostbindingpolicymanager-interface"></a>Интерфейс ICLRHostBindingPolicyManager

Предоставляет основному приложению методы для вычисления текущей политики привязки и обмена изменениями политики для указанной сборки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EvaluatePolicy](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|Оценивает политику привязки от имени узла.|  
|[Метод ModifyApplicationPolicy](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|Изменяет политику привязки для указанной сборки и создает новую версию политики.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Интерфейс IHostAssemblyStore](ihostassemblystore-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)

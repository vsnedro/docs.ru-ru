---
description: 'Дополнительные сведения о: интерфейс ICLRControl'
title: Интерфейс ICLRControl
ms.date: 03/30/2017
api_name:
- ICLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl
helpviewer_keywords:
- ICLRControl interface [.NET Framework hosting]
ms.assetid: a24fd905-1fa6-45a0-ad65-e9e2ee58861e
topic_type:
- apiref
ms.openlocfilehash: e108506d06b746d631f4c15c37d467399de30aba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637668"
---
# <a name="iclrcontrol-interface"></a>Интерфейс ICLRControl

Предоставляет методы, позволяющие узлу получать ссылки и настраивать аспекты среды CLR.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetCLRManager](iclrcontrol-getclrmanager-method.md)|Возвращает указатель интерфейса на экземпляр любого из типов диспетчера, который узел может использовать для настройки среды CLR.|  
|[Метод SetAppDomainManagerType](iclrcontrol-setappdomainmanagertype-method.md)|Задает тип, производный от <xref:System.AppDomainManager> типа для диспетчеров доменов приложений.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAssemblyIdentityManager](iclrassemblyidentitymanager-interface.md)
- [Интерфейс ICLRDebugManager](iclrdebugmanager-interface.md)
- [Интерфейс ICLRGCManager](iclrgcmanager-interface.md)
- [Интерфейс ICLRHostBindingPolicyManager](iclrhostbindingpolicymanager-interface.md)
- [Интерфейс ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md)
- [Интерфейс ICLROnEventManager](iclroneventmanager-interface.md)
- [Интерфейс ICLRPolicyManager](iclrpolicymanager-interface.md)
- [Интерфейс IHostControl](ihostcontrol-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)

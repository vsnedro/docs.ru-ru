---
title: Интерфейс ICLRDomainManager
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
ms.openlocfilehash: a5abb601fe795a0c615403eec69f68ad9f66f00f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95681175"
---
# <a name="iclrdomainmanager-interface"></a>Интерфейс ICLRDomainManager

Позволяет узлу указать Диспетчер домена приложения, который будет использоваться для инициализации домена приложения по умолчанию, а также для указания свойств инициализации.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md)|Задает тип, производный от <xref:System.AppDomainManager?displayProperty=nameWithType> класса диспетчера домена приложения, который будет использоваться для инициализации домена приложения по умолчанию.|  
|[Метод SetPropertiesForDefaultAppDomain](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|Задает свойства, которые будут использоваться для инициализации домена приложения по умолчанию.|  
  
## <a name="remarks"></a>Комментарии  

 Чтобы получить экземпляр этого интерфейса, вызовите метод [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) с типом менеджера IID `IID_ICLRDomainManager` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

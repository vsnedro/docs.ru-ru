---
description: 'Дополнительные сведения о: интерфейс Иклрдомаинманажер'
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
ms.openlocfilehash: d719e89d81e8c7abb1f238ce50b4e236de17ac72
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790013"
---
# <a name="iclrdomainmanager-interface"></a>Интерфейс ICLRDomainManager

Позволяет узлу указать Диспетчер домена приложения, который будет использоваться для инициализации домена приложения по умолчанию, а также для указания свойств инициализации.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод SetAppDomainManagerType](iclrdomainmanager-setappdomainmanagertype-method.md)|Задает тип, производный от <xref:System.AppDomainManager?displayProperty=nameWithType> класса диспетчера домена приложения, который будет использоваться для инициализации домена приложения по умолчанию.|  
|[Метод SetPropertiesForDefaultAppDomain](iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|Задает свойства, которые будут использоваться для инициализации домена приложения по умолчанию.|  
  
## <a name="remarks"></a>Remarks  

 Чтобы получить экземпляр этого интерфейса, вызовите метод [ICLRControl:: GetCLRManager](iclrcontrol-getclrmanager-method.md) с типом менеджера IID `IID_ICLRDomainManager` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

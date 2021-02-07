---
description: 'Дополнительные сведения о: Интерфейс IAppDomainSetup'
title: Интерфейс IAppDomainSetup
ms.date: 03/30/2017
api_name:
- IAppDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IAppDomainSetup
helpviewer_keywords:
- IAppDomainSetup interface [.NET Framework hosting]
ms.assetid: 1844da85-c031-40bf-bea4-1a3d12a36c8c
topic_type:
- apiref
ms.openlocfilehash: 8fd224308ea68f7b56ae174c7f71fc4f89630101
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760588"
---
# <a name="iappdomainsetup-interface"></a>Интерфейс IAppDomainSetup

Предоставляет свойства, позволяющие узлу настроить <xref:System.AppDomain?displayProperty=nameWithType> тип перед вызовом метода [ICorRuntimeHost:: CreateDomainEx](icorruntimehost-createdomainex-method.md) для его создания.  
  
## <a name="properties"></a>Свойства  
  
|Свойство|Описание|  
|--------------|-----------------|  
|<xref:System.AppDomainSetup.ApplicationBase%2A>|Возвращает или задает имя каталога, содержащего приложение.|  
|<xref:System.AppDomainSetup.ApplicationName%2A>|Возвращает или задает имя приложения.|  
|<xref:System.AppDomainSetup.CachePath%2A>|Возвращает или задает имя области, относящейся к приложению, в котором файлы копируются при теневом копировании.|  
|<xref:System.AppDomainSetup.ConfigurationFile%2A>|Возвращает или задает имя файла конфигурации для приложения.|  
|<xref:System.AppDomainSetup.DynamicBase%2A>|Возвращает или задает имя каталога, в котором хранятся и обращаются динамически создаваемые файлы.|  
|<xref:System.AppDomainSetup.LicenseFile%2A>|Возвращает или задает путь к файлу лицензии, связанному с этим доменом.|  
|<xref:System.AppDomainSetup.PrivateBinPath%2A>|Возвращает или задает список каталогов в сочетании с <xref:System.AppDomainSetup.ApplicationBase%2A> каталогом для проверки закрытых сборок.|  
|<xref:System.AppDomainSetup.PrivateBinPathProbe%2A>|Возвращает или задает строковое значение, которое включает или исключает <xref:System.AppDomainSetup.ApplicationBase%2A> из пути поиска для приложения.|  
|<xref:System.AppDomainSetup.ShadowCopyDirectories%2A>|Возвращает или задает имена каталогов, содержащих сборки для теневого копирования.|  
|<xref:System.AppDomainSetup.ShadowCopyFiles%2A>|Возвращает или задает строку, которая указывает, включено ли теневое копирование. Допустимые значения: "true" или "false".|  
  
## <a name="remarks"></a>Remarks  

 `IAppDomainSetup`Интерфейс соответствует управляемому <xref:System.IAppDomainSetup> интерфейсу, который <xref:System.AppDomainSetup> реализуется типом. <xref:System.IAppDomainSetup?displayProperty=nameWithType>Подробные описания его свойств см. в разделе.  
  
 `IAppDomainSetup` представляет сведения о привязке сборки, которые можно добавить к <xref:System.AppDomain> экземпляру перед его созданием. Например, узел может установить <xref:System.AppDomainSetup.ApplicationBase%2A> свойство, чтобы установить корневой каталог, который проверяет среда CLR для управляемых сборок.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup>
- [Интерфейсы размещения](hosting-interfaces.md)

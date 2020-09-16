---
title: Интерфейс ICorRuntimeHost
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost
helpviewer_keywords:
- ICorRuntimeHost interface [.NET Framework hosting]
ms.assetid: 4369533d-7834-4497-bc37-bfea0ad737b1
topic_type:
- apiref
ms.openlocfilehash: 420f22a242a20f8bdf5d5b84f47a297a2f503db0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546025"
---
# <a name="icorruntimehost-interface"></a>Интерфейс ICorRuntimeHost
Предоставляет методы, позволяющие основному приложению запускать и прекращать работу среды CLR, создавать и настраивать домены приложений, получать доступ к домену по умолчанию и перечислять все домены, выполняющиеся в процессе.  
  
 В .NET Framework версии 2,0 этот интерфейс заменен [ICLRRuntimeHost](iclrruntimehost-interface.md).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CloseEnum](icorruntimehost-closeenum-method.md)|Сбрасывает перечислитель домена обратно в начало списка доменов.|  
|[Метод CreateDomain](icorruntimehost-createdomain-method.md)|Создает домен приложения. Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain> на экземпляр типа <xref:System.AppDomain?displayProperty=nameWithType> .|  
|[Метод CreateDomainEx](icorruntimehost-createdomainex-method.md)|Создает домен приложения. Этот метод позволяет вызывающему объекту передать экземпляр IAppDomainSetup для настройки дополнительных функций возвращаемого <xref:System._AppDomain> экземпляра.|  
|[Метод CreateDomainSetup](icorruntimehost-createdomainsetup-method.md)|Возвращает указатель интерфейса типа `IAppDomainSetup` на <xref:System.AppDomainSetup> экземпляр. `IAppDomainSetup` предоставляет методы для настройки аспектов домена приложения перед его созданием.|  
|[Метод CreateEvidence](icorruntimehost-createevidence-method.md)|Возвращает указатель интерфейса типа <xref:System.Security.Principal.IIdentity> , который позволяет основному приложению создавать доказательства безопасности для передачи в [CreateDomain](icorruntimehost-createdomain-method.md) или [CreateDomainEx](icorruntimehost-createdomainex-method.md).|  
|[Метод CreateLogicalThreadState](icorruntimehost-createlogicalthreadstate-method.md)|Не используется.|  
|[Метод CurrentDomain](icorruntimehost-currentdomain-method.md)|Возвращает указатель интерфейса типа <xref:System._AppDomain> , который представляет домен, загруженный в текущем потоке.|  
|[Метод DeleteLogicalThreadState](icorruntimehost-deletelogicalthreadstate-method.md)|Не используется.|  
|[Метод EnumDomains](icorruntimehost-enumdomains-method.md)|Возвращает перечислитель для доменов в текущем процессе.|  
|[Метод GetConfiguration](icorruntimehost-getconfiguration-method.md)|Возвращает объект, позволяющий ведущему приложению указать конфигурацию обратного вызова среды CLR.|  
|[Метод GetDefaultDomain](icorruntimehost-getdefaultdomain-method.md)|Возвращает указатель интерфейса типа <xref:System._AppDomain> , представляющий домен по умолчанию для текущего процесса.|  
|[Метод LocksHeldByLogicalThread](icorruntimehost-locksheldbylogicalthread-method.md)|Не используется.|  
|[Метод MapFile](icorruntimehost-mapfile-method.md)|Сопоставляет указанный файл с памятью. Этот метод устарел.|  
|[Метод NextDomain](icorruntimehost-nextdomain-method.md)|Возвращает указатель интерфейса на следующий домен в перечислении.|  
|[Метод Start](icorruntimehost-start-method.md)|Запускает среду CLR.|  
|[Метод завершения](icorruntimehost-stop-method.md)|Останавливает выполнение кода в среде выполнения для текущего процесса.|  
|[Метод SwitchInLogicalThreadState](icorruntimehost-switchinlogicalthreadstate-method.md)|Не используется.|  
|[Метод SwitchOutLogicalThreadState](icorruntimehost-switchoutlogicalthreadstate-method.md)|Не используется.|  
|[Метод UnloadDomain](icorruntimehost-unloaddomain-method.md)|Выгружает указанный домен приложения из текущего процесса.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:** 1,0, 1,1  
  
## <a name="see-also"></a>См. также

- <xref:System.AppDomain>
- [Размещение](index.md)
- [Интерфейс ICLRRuntimeHost](iclrruntimehost-interface.md)
- [Хост-приложения среды выполнения](/previous-versions/dotnet/netframework-4.0/a51xd4ze(v=vs.100))
- [Интерфейсы размещения](hosting-interfaces.md)
- [Компонентный класс CorRuntimeHost](corruntimehost-coclass.md)

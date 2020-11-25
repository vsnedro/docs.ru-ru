---
title: Интерфейс ICLRRuntimeHost
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost
helpviewer_keywords:
- ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: cb0c5f65-3791-47bc-b833-2f84f4101ba5
topic_type:
- apiref
ms.openlocfilehash: 8d88222215eb31e1c63f3b26079517c4b088e81b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728840"
---
# <a name="iclrruntimehost-interface"></a>Интерфейс ICLRRuntimeHost

Предоставляет функциональные возможности, аналогичные интерфейсу [ICorRuntimeHost](icorruntimehost-interface.md) , предоставленному в .NET Framework версии 1, со следующими изменениями:  
  
- Добавление метода [SetHostControl](iclrruntimehost-sethostcontrol-method.md) для задания интерфейса элемента управления ведущего приложения.  
  
- Пропуск некоторых методов, предоставляемых `ICorRuntimeHost` .  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ExecuteApplication](iclrruntimehost-executeapplication-method.md)|Используется в сценариях развертывания ClickOnce на основе манифеста для указания приложения, которое должно быть активировано в новом домене.|  
|[Метод ExecuteInAppDomain](iclrruntimehost-executeinappdomain-method.md)|Указывает, <xref:System.AppDomain> в котором следует выполнить указанный управляемый код.|  
|[Метод ExecuteInDefaultAppDomain](iclrruntimehost-executeindefaultappdomain-method.md)|Вызывает указанный метод указанного типа в указанной сборке.|  
|[Метод GetCLRControl](iclrruntimehost-getclrcontrol-method.md)|Возвращает указатель интерфейса типа [ICLRControl](iclrcontrol-interface.md) , который может использоваться узлами для настройки аспектов среды CLR.|  
|[Метод GetCurrentAppDomainId](iclrruntimehost-getcurrentappdomainid-method.md)|Возвращает числовой идентификатор объекта <xref:System.AppDomain> , который выполняется в данный момент.|  
|[Метод SetHostControl](iclrruntimehost-sethostcontrol-method.md)|Задает интерфейс элемента управления ведущего приложения. `SetHostControl`Перед вызовом необходимо вызвать `Start` .|  
|[Метод Start](iclrruntimehost-start-method.md)|Инициализирует среду CLR в процессе.|  
|[Метод Stop](iclrruntimehost-stop-method.md)|Останавливает выполнение кода средой выполнения.|  
|[Метод UnloadAppDomain](iclrruntimehost-unloadappdomain-method.md)|Выгружает объект <xref:System.AppDomain> , соответствующий указанному числовому идентификатору.|  
  
## <a name="remarks"></a>Комментарии  

 Начиная с .NET Framework 4, используйте интерфейс [ICLRMetaHost](iclrmetahost-interface.md) для получения указателя на интерфейс [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , а затем вызовите метод [ICLRRuntimeInfo::-interface](iclrruntimeinfo-getinterface-method.md) , чтобы получить указатель на `ICLRRuntimeHost` . В более ранних версиях .NET Framework узел получает указатель на `ICLRRuntimeHost` экземпляр, вызывая [CorBindToRuntimeEx](corbindtoruntimeex-function.md) или [корбиндтокуррентрунтиме](corbindtocurrentruntime-function.md). Чтобы реализовать реализации любой из технологий, предоставляемых в .NET Framework версии 2,0, необходимо использовать `ICLRRuntimeHost` вместо `ICorRuntimeHost` .  
  
> [!IMPORTANT]
> Не вызывайте метод [Start](iclrruntimehost-start-method.md) перед вызовом метода [ExecuteApplication](iclrruntimehost-executeapplication-method.md) для активации приложения на основе манифеста. Если `Start` метод вызывается первым, `ExecuteApplication` вызов метода завершится ошибкой.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Функция CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)
- [Функция CorBindToRuntimeEx](corbindtoruntimeex-function.md)
- [Интерфейс ICLRControl](iclrcontrol-interface.md)
- [Интерфейс ICorRuntimeHost](icorruntimehost-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Кокласс CLRRuntimeHost](clrruntimehost-coclass.md)

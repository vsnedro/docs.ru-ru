---
title: Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5
ms.date: 03/30/2017
helpviewer_keywords:
- hosting interfaces [.NET Framework], version 4
- .NET Framework 4, hosting interfaces
- interfaces [.NET Framework hosting], version 4
ms.assetid: f6af6116-f5b0-4bda-a276-fffdba70893d
ms.openlocfilehash: a524c0b0e01fbde95ce2341874511960b3e5738e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616857"
---
# <a name="clr-hosting-interfaces-added-in-the-net-framework-4-and-45"></a>Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5
В этом разделе описываются интерфейсы, которые могут использоваться неуправляемыми узлами для интеграции среды CLR в .NET Framework 4, .NET Framework 4,5 и более поздних версий в свои приложения. Эти интерфейсы предоставляют основному приложению методы для настройки и загрузки среды выполнения в процесс.  
  
 Начиная с .NET Framework 4, все интерфейсы размещения имеют следующие характеристики.  
  
- Они используют управление жизненным циклом ( `AddRef` и `Release` ), инкапсуляцию (неявный контекст) и `QueryInterface` из com.  
  
- Они не используют типы COM, такие как `BSTR` , `SAFEARRAY` или `VARIANT` .  
  
- Нет моделей апартамента, агрегирования или активации реестра, использующих [функцию CoCreateInstance](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstance).  
  
## <a name="in-this-section"></a>в этом разделе  
 [Интерфейс ICLRAppDomainResourceMonitor](iclrappdomainresourcemonitor-interface.md)  
 Предоставляет методы для проверки использования памяти и ЦП домена приложения.  
  
 [Интерфейс ICLRDomainManager](iclrdomainmanager-interface.md)  
 Позволяет узлу указать Диспетчер домена приложения, который будет использоваться для инициализации домена приложения по умолчанию, а также для указания свойств инициализации.  
  
 [Интерфейс ICLRGCManager2](iclrgcmanager2-interface.md)  
 Предоставляет метод [SetGCStartupLimitsEx](iclrgcmanager2-setgcstartuplimitsex-method.md) , который позволяет основному приложению задать размер сегмента сборки мусора и максимальный размер поколения 0 в результате создания системы сборки мусора для значений, превышающих `DWORD` .  
  
 [Интерфейс ICLRMetaHost](iclrmetahost-interface.md)  
 Предоставляет методы, возвращающие определенную версию среды CLR, список всех установленных CLR, список всех выполняемых в процессе сред выполнения, возвращение интерфейса активации и обнаружение версии среды CLR, используемой для компиляции сборки.  
  
 [Интерфейс ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)  
 Предоставляет метод [GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) , ПРЕДОСТАВЛЯЮЩИЙ интерфейс CLR на основе критериев политики, управляемой сборки, версии и файла конфигурации.  
  
 [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)  
 Предоставляет методы, возвращающие сведения о конкретной среде выполнения, включая версию, каталог и состояние загрузки.  
  
 [Интерфейс ICLRStrongName](iclrstrongname-interface.md)  
 Предоставляет базовые глобальные статические функции для подписи сборок со строгими именами. Все методы [метод iclrstrongname](iclrstrongname-interface.md) возвращают стандартные значения HRESULT для com.  
  
 [Интерфейс ICLRStrongName2](iclrstrongname2-interface.md)  
 Предоставляет возможность создания строгих имен с помощью группы SHA-2 алгоритмов безопасных хэширования (SHA-256, SHA-384 и SHA-512).  
  
 [Интерфейс ICLRTask2](iclrtask2-interface.md)  
 Предоставляет все функциональные возможности [интерфейса ICLRTask](iclrtask-interface.md); Кроме того, предоставляет методы, которые позволяют задерживать прерывания потока в текущем потоке.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Устаревшие интерфейсы размещения CLR и CoClasses](deprecated-clr-hosting-interfaces-and-coclasses.md)  
 Описание интерфейсов размещения, поставляемых с .NET Framework версиями 1,0 и 1,1.  
  
 [Интерфейсы размещения CLR](clr-hosting-interfaces.md)  
 Описывает интерфейсы размещения, предоставляемые с .NET Framework версиями 2,0, 3,0 и 3,5.  
  
 [Размещение](index.md)  
 Введение в размещение в .NET Framework.

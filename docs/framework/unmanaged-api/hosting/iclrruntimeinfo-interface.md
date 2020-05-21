---
title: Интерфейс ICLRRuntimeInfo
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo
helpviewer_keywords:
- ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 287e5ede-b3a7-4ef8-a756-4fca3f285a82
topic_type:
- apiref
ms.openlocfilehash: cafb85ed5f6a1245dd520ab3a5e94f95c8d37608
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762556"
---
# <a name="iclrruntimeinfo-interface"></a>Интерфейс ICLRRuntimeInfo
Предоставляет методы, возвращающие сведения о конкретной среде CLR, включая версию, каталог и состояние загрузки. Этот интерфейс также предоставляет специальные функции среды выполнения без инициализации среды выполнения. Он включает метод [LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) , относительный во время выполнения, метод [GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) для конкретного модуля среды выполнения и интерфейсы, предоставляемые средой выполнения, [через метод метода](iclrruntimeinfo-getinterface-method.md) WebMethod.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md)|Привязывает эту среду выполнения для всех устаревших решений политики активации CLR версии 2.|  
|[Метод GetDefaultStartupFlags](iclrruntimeinfo-getdefaultstartupflags-method.md)|Получает флаги запуска среды CLR и файл конфигурации узла.|  
|[Метод GetInterface](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getinterface-method.md)|Загружает среду CLR в текущий процесс и возвращает указатели на интерфейсы среды выполнения, такие как [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md), [метод iclrstrongname](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md) и [IMetaDataDispenser](../metadata/imetadatadispenser-interface.md). Этот метод заменяет все `CorBindTo*` функции.|  
|[Метод GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md)|Возвращает адрес указанной функции, которая была экспортирована из среды CLR, связанной с этим интерфейсом. Этот метод заменяет метод [жетреалпрокаддресс](getrealprocaddress-function.md) .|  
|[Метод GetRuntimeDirectory](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getruntimedirectory-method.md)|Возвращает каталог установки среды CLR, связанной с этим интерфейсом. Этот метод заменяет метод [GetCORSystemDirectory](getcorsystemdirectory-function.md) .|  
|[Метод GetVersionString](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getversionstring-method.md)|Возвращает сведения о версии среды CLR, связанные с заданным интерфейсом [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) . Этот метод заменяет методы [GetRequestedRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md) и [жетрекуестедрунтимеверсион](getrequestedruntimeversion-function.md) .|  
|[Метод IsLoadable](iclrruntimeinfo-isloadable-method.md)|Указывает, можно ли загрузить среду выполнения, связанную с этим интерфейсом, в текущий процесс, принимая во внимание другие среды выполнения, которые уже могут быть загружены в процесс.|  
|[Метод IsLoaded](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isloaded-method.md)|Указывает, загружается ли среда CLR, связанная с интерфейсом [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , в процесс.|  
|[Метод IsStarted](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-isstarted-method.md)|Указывает, запущена ли среда CLR, связанная с интерфейсом [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .|  
|[Метод LoadErrorString](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loaderrorstring-method.md)|Преобразует значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров. Этот метод заменяет методы [лоадстрингрк](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md) и [лоадстрингрцекс](loadstringrcex-function.md) .|  
|[Метод LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md)|Загружает библиотеку из каталога платформы среды CLR, представленной интерфейсом [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) . Этот метод заменяет метод [лоадлибраришим](loadlibraryshim-function.md) .|  
|[Метод SetDefaultStartupFlags](iclrruntimeinfo-setdefaultstartupflags-method.md)|Задает флаги запуска среды CLR и файл конфигурации узла.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

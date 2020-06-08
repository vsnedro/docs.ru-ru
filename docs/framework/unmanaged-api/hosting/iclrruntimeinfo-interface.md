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
ms.openlocfilehash: 71e2c7f6790f29872c051bb5cea50755068057e9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504047"
---
# <a name="iclrruntimeinfo-interface"></a>Интерфейс ICLRRuntimeInfo
Предоставляет методы, возвращающие сведения о конкретной среде CLR, включая версию, каталог и состояние загрузки. Этот интерфейс также предоставляет специальные функции среды выполнения без инициализации среды выполнения. Он включает метод [LoadLibrary](iclrruntimeinfo-loadlibrary-method.md) , относительный во время выполнения, метод [GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) для конкретного модуля среды выполнения и интерфейсы, предоставляемые средой выполнения, [через метод метода](iclrruntimeinfo-getinterface-method.md) WebMethod.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md)|Привязывает эту среду выполнения для всех устаревших решений политики активации CLR версии 2.|  
|[Метод GetDefaultStartupFlags](iclrruntimeinfo-getdefaultstartupflags-method.md)|Получает флаги запуска среды CLR и файл конфигурации узла.|  
|[Метод GetInterface](iclrruntimeinfo-getinterface-method.md)|Загружает среду CLR в текущий процесс и возвращает указатели на интерфейсы среды выполнения, такие как [ICLRRuntimeHost](iclrruntimehost-interface.md), [метод iclrstrongname](iclrstrongname-interface.md) и [IMetaDataDispenser](../metadata/imetadatadispenser-interface.md). Этот метод заменяет все `CorBindTo*` функции.|  
|[Метод GetProcAddress](iclrruntimeinfo-getprocaddress-method.md)|Возвращает адрес указанной функции, которая была экспортирована из среды CLR, связанной с этим интерфейсом. Этот метод заменяет метод [жетреалпрокаддресс](getrealprocaddress-function.md) .|  
|[Метод GetRuntimeDirectory](iclrruntimeinfo-getruntimedirectory-method.md)|Возвращает каталог установки среды CLR, связанной с этим интерфейсом. Этот метод заменяет метод [GetCORSystemDirectory](getcorsystemdirectory-function.md) .|  
|[Метод GetVersionString](iclrruntimeinfo-getversionstring-method.md)|Возвращает сведения о версии среды CLR, связанные с заданным интерфейсом [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) . Этот метод заменяет методы [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md) и [жетрекуестедрунтимеверсион](getrequestedruntimeversion-function.md) .|  
|[Метод IsLoadable](iclrruntimeinfo-isloadable-method.md)|Указывает, можно ли загрузить среду выполнения, связанную с этим интерфейсом, в текущий процесс, принимая во внимание другие среды выполнения, которые уже могут быть загружены в процесс.|  
|[Метод IsLoaded](iclrruntimeinfo-isloaded-method.md)|Указывает, загружается ли среда CLR, связанная с интерфейсом [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , в процесс.|  
|[Метод IsStarted](iclrruntimeinfo-isstarted-method.md)|Указывает, запущена ли среда CLR, связанная с интерфейсом [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .|  
|[Метод LoadErrorString](iclrruntimeinfo-loaderrorstring-method.md)|Преобразует значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров. Этот метод заменяет методы [лоадстрингрк](loadstringrc-function.md) и [лоадстрингрцекс](loadstringrcex-function.md) .|  
|[Метод LoadLibrary](iclrruntimeinfo-loadlibrary-method.md)|Загружает библиотеку из каталога платформы среды CLR, представленной интерфейсом [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) . Этот метод заменяет метод [лоадлибраришим](loadlibraryshim-function.md) .|  
|[Метод SetDefaultStartupFlags](iclrruntimeinfo-setdefaultstartupflags-method.md)|Задает флаги запуска среды CLR и файл конфигурации узла.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

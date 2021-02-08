---
description: 'Дополнительные сведения: метод ICLRRuntimeInfo:: Сетдефаултстартупфлагс'
title: Метод ICLRRuntimeInfo::SetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
ms.openlocfilehash: eb839b2ff71836adc1b3858092f7caf5787275b1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785046"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a>Метод ICLRRuntimeInfo::SetDefaultStartupFlags

Задает флаги запуска и файл конфигурации узла, который будет использоваться для запуска среды выполнения. Этот метод заменяет использование `startupFlags` параметра в функциях [CorBindToRuntimeEx](corbindtoruntimeex-function.md) и [корбиндторунтимехост](corbindtoruntimehost-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwStartupFlags`  
 окне Заданные флаги запуска узла. Используйте те же флаги, что и для функций [CorBindToRuntimeEx](corbindtoruntimeex-function.md) и [корбиндторунтимехост](corbindtoruntimehost-function.md) .  
  
 `pwzHostConfigFile`  
 окне Путь к каталогу устанавливаемого файла конфигурации узла.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующее конкретное значение HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
  
## <a name="remarks"></a>Remarks  

 Многопоточный узел должен синхронизировать вызовы этого метода. В противном случае поток A может вызвать `SetStartupFlags` метод после того, как поток б завершит вызов `SetStartupFlags` и до того, как поток b запустит среду выполнения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

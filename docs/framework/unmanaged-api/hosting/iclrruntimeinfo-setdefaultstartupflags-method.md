---
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
ms.openlocfilehash: 7d201962976d198372226eb686696fcdccf3eb69
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762166"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a>Метод ICLRRuntimeInfo::SetDefaultStartupFlags
Задает флаги запуска и файл конфигурации узла, который будет использоваться для запуска среды выполнения. Этот метод заменяет использование `startupFlags` параметра в функциях [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) и [корбиндторунтимехост](corbindtoruntimehost-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a>Параметры  
 `dwStartupFlags`  
 окне Заданные флаги запуска узла. Используйте те же флаги, что и для функций [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) и [корбиндторунтимехост](corbindtoruntimehost-function.md) .  
  
 `pwzHostConfigFile`  
 окне Путь к каталогу устанавливаемого файла конфигурации узла.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующее конкретное значение HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
  
## <a name="remarks"></a>Комментарии  
 Многопоточный узел должен синхронизировать вызовы этого метода. В противном случае поток A может вызвать `SetStartupFlags` метод после того, как поток б завершит вызов `SetStartupFlags` и до того, как поток b запустит среду выполнения.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

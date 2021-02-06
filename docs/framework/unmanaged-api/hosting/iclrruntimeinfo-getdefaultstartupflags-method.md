---
description: 'Дополнительные сведения: метод ICLRRuntimeInfo:: Жетдефаултстартупфлагс'
title: Метод ICLRRuntimeInfo::GetDefaultStartupFlags
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
ms.openlocfilehash: c6afb19319fd24d499c2c216f2ce0adc2e7a886c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637183"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a>Метод ICLRRuntimeInfo::GetDefaultStartupFlags

Возвращает флаги запуска и файл конфигурации узла, которые будут использоваться для запуска среды выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a>Параметры  

 `pdwStartupFlags`  
 заполняет Указатель на установленные в данный момент флаги запуска узла.  
  
 `pwzHostConfigFile`  
 заполняет Указатель на путь к каталогу текущего файла конфигурации узла.  
  
 `pcchHostConfigFile`  
 [вход, выход] Во входных данных — размер `pwzHostConfigFile` , чтобы избежать переполнения буфера. Если `pwzHostConfigFile` имеет значение null, метод возвращает требуемый размер `pwzHostConfigFile` для предварительного выделения.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующее конкретное значение HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
  
## <a name="remarks"></a>Remarks  

 Этот метод возвращает значения флагов по умолчанию ( `STARTUP_CONCURRENT_GC` и `NULL` ) или значения, предоставленные предыдущим вызовом [метода ICLRRuntimeInfo:: сетдефаултстартупфлагс](iclrruntimeinfo-setdefaultstartupflags-method.md), или значения, заданные любыми `CorBind*` методами, если они привязаны к этой среде выполнения.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

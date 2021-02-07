---
description: 'Дополнительные сведения о методе: ICLRAppDomainResourceMonitor:: GetCurrentCpuTime'
title: Метод ICLRAppDomainResourceMonitor::GetCurrentCpuTime
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
ms.openlocfilehash: ce36bf4ab88f953834d3ff12404bcaadcb42812d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753933"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a>Метод ICLRAppDomainResourceMonitor::GetCurrentCpuTime

Возвращает общее время процессора, которое использовалось всеми потоками во время выполнения в текущем домене приложения, так как был создан домен приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a>Параметры  

 `dwAppDomainId`  
 окне ИДЕНТИФИКАТОР запрошенного домена приложения.  
  
 `pMilliseconds`  
 заполняет Указатель на общее время процессора, которое использовалось всеми потоками при выполнении в текущем домене приложения с момента создания домена приложения. Этот параметр может иметь значение `null`.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|COR_E_APPDOMAINUNLOADED|Домен приложения был выгружен или не существует.|  
|E_FAIL|Отслеживание ресурсов домена приложений не включено.<br /><br /> -или-<br /><br /> Все остальные сбои.|  
  
## <a name="remarks"></a>Remarks  

 Этот метод является неуправляемым эквивалентом управляемого <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> Свойства.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRAppDomainResourceMonitor](iclrappdomainresourcemonitor-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Мониторинг ресурсов домена приложения](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Размещение](index.md)

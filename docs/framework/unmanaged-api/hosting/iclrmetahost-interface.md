---
description: 'Дополнительные сведения о: интерфейс ICLRMetaHost'
title: Интерфейс ICLRMetaHost
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
ms.openlocfilehash: 5dc50af85c067bcb525414e47cddd34070b83a27
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637512"
---
# <a name="iclrmetahost-interface"></a>Интерфейс ICLRMetaHost

Предоставляет методы, возвращающие определенную версию среды CLR на основе ее номера версии, список всех установленных CLR, список всех сред выполнения, загруженных в указанный процесс, обнаружение версии среды CLR, используемой для компиляции сборки, выхода из процесса с чистым завершением работы среды выполнения и запроса привязки API прежних версий.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateInstalledRuntimes](iclrmetahost-enumerateinstalledruntimes-method.md)|Возвращает перечисление, содержащее допустимый указатель интерфейса [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) для каждой версии среды CLR, установленной на компьютере.|  
|[Метод EnumerateLoadedRuntimes](iclrmetahost-enumerateloadedruntimes-method.md)|Возвращает перечисление, содержащее допустимый указатель интерфейса [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) для каждой среды CLR, загруженной в заданный процесс. Этот метод заменяет [GetVersionFromProcess](getversionfromprocess-function.md).|  
|[Метод ExitProcess](iclrmetahost-exitprocess-method.md)|Пытается корректно завершить работу всех загруженных сред выполнения, а затем завершить процесс. Заменяет функцию [корекситпроцесс](corexitprocess-function.md) .|  
|[Метод GetRuntime](iclrmetahost-getruntime-method.md)|Возвращает интерфейс [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , соответствующий определенной версии среды CLR. Этот метод заменяет функцию [CorBindToRuntimeEx](corbindtoruntimeex-function.md) , используемую с флагом [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .|  
|[Метод GetVersionFromFile](iclrmetahost-getversionfromfile-method.md)|Возвращает исходную версию компиляции платформа .NET Framework сборки (хранится в метаданных) по указанному пути к файлу. Этот метод заменяет [жетфилеверсион](getfileversion-function.md).|  
|[Метод QueryLegacyV2RuntimeBinding](iclrmetahost-querylegacyv2runtimebinding-method.md)|Возвращает интерфейс, представляющий среду выполнения, к которой привязана политика устаревшей активации, например, с помощью `useLegacyV2RuntimeActivationPolicy` атрибута в записи файла конфигурации [ \<startup> элемента](../../configure-apps/file-schema/startup/startup-element.md) , путем непосредственного использования устаревших API-интерфейсов активации или путем вызова метода [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) .|  
|[Метод RequestRuntimeLoadedNotification](iclrmetahost-requestruntimeloadednotification-method.md)|Гарантирует обратный вызов к указанному указателю функции при первой загрузке версии среды CLR, но еще не запущенной. Этот метод заменяет [локкклрверсион](lockclrversion-function.md)|  
  
## <a name="remarks"></a>Remarks  

 Единственный способ получить экземпляр этого интерфейса — вызвать функцию [клркреатеинстанце](clrcreateinstance-function.md) следующим образом:  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

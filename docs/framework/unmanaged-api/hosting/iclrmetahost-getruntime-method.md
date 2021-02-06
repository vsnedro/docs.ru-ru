---
description: 'Дополнительные сведения о методе: ICLRMetaHost:: Runtime'
title: Метод ICLRMetaHost::GetRuntime
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetRuntime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type:
- apiref
ms.openlocfilehash: 8a2ada652dbb139337150cb8ed20986ebf8ae7f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637525"
---
# <a name="iclrmetahostgetruntime-method"></a>Метод ICLRMetaHost::GetRuntime

Возвращает интерфейс [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , соответствующий определенной версии среды CLR. Этот метод заменяет функцию [CorBindToRuntimeEx](corbindtoruntimeex-function.md) , используемую с флагом [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in] REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pwzVersion`  
 окне Версия компиляции платформа .NET Framework, хранящаяся в метаданных, в формате "v *A*. *B*[.*X*] ". *A*, *B* и *X* — это десятичные числа, соответствующие основной версии, дополнительной версии и номеру сборки.  
  
> [!NOTE]
> Этот параметр должен соответствовать имени каталога для платформа .NET Framework версии, так как она отображается в разделе К:\виндовс\микрософт.нет\фрамеворк или C:\Windows\Microsoft.NET\Framework64.  
  
 Примеры значений: "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" и "v 4.0. *X*", где *X* зависит от установленного номера сборки. Требуется префикс "v".  
  
 `riid`  
 окне Идентификатор требуемого интерфейса. В настоящее время единственным допустимым значением для этого параметра является IID_ICLRRuntimeInfo.  
  
 `ppRuntime`  
 заполняет Указатель на интерфейс [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , соответствующий запрошенной среде выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|`pwzVersion` или `ppRuntime` равно null.|  
  
## <a name="remarks"></a>Remarks  

 Этот метод взаимодействует согласованно с устаревшими интерфейсами, такими как интерфейс [ICorRuntimeHost](icorruntimehost-interface.md) , и устаревшими функциями, такими как устаревшие `CorBindTo*` функции (см. статью [устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md) в API размещения платформа .NET Framework 2,0). То есть среды выполнения, загруженные с помощью API прежних версий, видимы для нового API, а среды выполнения, которые загружаются с новым API, видимы для API прежних версий.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRMetaHost](iclrmetahost-interface.md)
- [Устаревшие интерфейсы размещения CLR и CoClasses](deprecated-clr-hosting-interfaces-and-coclasses.md)
- [Интерфейсы размещения CLR](clr-hosting-interfaces.md)
- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)
- [Размещение](index.md)

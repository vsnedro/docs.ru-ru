---
title: Метод ICLRMetaHost::EnumerateLoadedRuntimes
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
ms.openlocfilehash: 7b09bb9c3abcb23997bfd412c3ea939404e583c1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504177"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a>Метод ICLRMetaHost::EnumerateLoadedRuntimes
Возвращает перечисление, содержащее допустимый указатель интерфейса [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) для каждой версии среды CLR, загруженной в заданный процесс. Этот метод заменяет функцию [GetVersionFromProcess](getversionfromprocess-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `hndProcess`  
 окне Описатель процесса для проверки загруженных сред выполнения.  
  
 `ppEnumerator`  
 заполняет <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown>Перечисление интерфейсов [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) , соответствующих каждой среде CLR, загруженной процессом.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `ppEnumerator` имеет значение NULL.|  
  
## <a name="remarks"></a>Примечания  
 Этот метод перечисляет все загруженные среды выполнения, даже если они были загружены с устаревшими функциями, такими как [CorBindToRuntime](corbindtoruntime-function.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRMetaHost](iclrmetahost-interface.md)
- [Размещение](index.md)

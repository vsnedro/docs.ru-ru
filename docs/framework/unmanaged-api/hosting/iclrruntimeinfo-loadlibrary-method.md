---
title: Метод ICLRRuntimeInfo::LoadLibrary
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
ms.openlocfilehash: 09c80c3a56d86943ebe00e5222bb5452ab44e150
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762179"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a>Метод ICLRRuntimeInfo::LoadLibrary
Загружает библиотеку .NET Framework из среды CLR, представленной интерфейсом [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .  
  
 Этот метод заменяет функцию [лоадлибраришим](loadlibraryshim-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzDllName`  
 окне Имя загружаемой сборки.  
  
 `phndModule`  
 заполняет Маркер загруженной сборки.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|`pwzDllName` или `phndModule` равно null.|  
|E_OUTOFMEMORY|Недостаточно памяти для выполнения запроса.|  
  
## <a name="remarks"></a>Комментарии  
 Этот метод загружает только библиотеки DLL, входящие в распространяемый пакет .NET Framework. Он не может загружать сборки, созданные пользователем.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

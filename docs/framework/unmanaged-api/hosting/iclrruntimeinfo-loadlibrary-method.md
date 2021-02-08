---
description: 'Дополнительные сведения: метод ICLRRuntimeInfo:: LoadLibrary'
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
ms.openlocfilehash: 47557934868c7c1b68b23bf4eded0e90705d7252
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785059"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a>Метод ICLRRuntimeInfo::LoadLibrary

Загружает библиотеку платформа .NET Framework из среды CLR, представленной интерфейсом [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .  
  
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
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|`pwzDllName` или `phndModule` равно null.|  
|E_OUTOFMEMORY|Недостаточно памяти для выполнения запроса.|  
  
## <a name="remarks"></a>Remarks  

 Этот метод загружает только библиотеки DLL, входящие в распространяемый пакет платформа .NET Framework. Он не может загружать сборки, созданные пользователем.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

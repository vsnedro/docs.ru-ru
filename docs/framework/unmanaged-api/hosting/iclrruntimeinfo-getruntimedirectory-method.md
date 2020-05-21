---
title: Метод ICLRRuntimeInfo::GetRuntimeDirectory
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
ms.openlocfilehash: d744abf5c502e9b9510cf9fd6479149b6c2177cc
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762218"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a>Метод ICLRRuntimeInfo::GetRuntimeDirectory
Возвращает каталог установки среды CLR, связанной с этим интерфейсом.  
  
 Этот метод заменяет функцию [GetCORSystemDirectory](getcorsystemdirectory-function.md) , указанную в .NET Framework версиях 2,0, 3,0 и 3,5.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzBuffer`  
 заполняет Возвращает каталог установки среды CLR. Путь установки является полным; Например, "c:\windows\microsoft.net\framework\v1.0.3705 \\ ".  
  
 `pchBuffer`  
 [вход, выход] Указывает размер `pwzBuffer` во избежание переполнения буфера. Если `pwzBuffer` параметр имеет значение null, `pchBuffer` возвращает требуемый размер `pwzBuffer` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|`pwzBuffer` или `pchBuffer` равно null.|  
  
## <a name="remarks"></a>Remarks  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Размещение](index.md)

---
title: Метод ICLRRuntimeInfo::LoadErrorString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
ms.openlocfilehash: da6efae38cd70a68feea56b12e86be23fde7f0cb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762192"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a>Метод ICLRRuntimeInfo::LoadErrorString
Преобразует значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.  
  
 Этот метод заменяет следующие функции:  
  
- [лоадстрингрк](loadstringrc-function.md)  
  
- [лоадстрингрцекс](loadstringrcex-function.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a>Параметры  
 `iResourceID`  
 окне Значение HRESULT для преобразования.  
  
 `pwzBuffer`  
 заполняет Строка сообщения, связанная с данным значением HRESULT.  
  
 `pcchBuffer`  
 [вход, выход] Размер `pwzbuffer` во избежание переполнения буфера. Если `pwzbuffer` параметр имеет значение null, `pcchBuffer` то предоставляет ожидаемый размер `pwzbuffer` для разрешения предварительного выделения.  
  
 `iLocaleID`  
 окне Идентификатор языка и региональных параметров. Чтобы использовать язык и региональные параметры по умолчанию, необходимо указать значение-1.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|Параметр `pcchBuffer` имеет значение NULL.|  
|E_INVALIDARG|Параметр `pwzBuffer` имеет значение NULL.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

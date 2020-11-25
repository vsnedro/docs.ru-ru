---
title: Метод ICLRRuntimeInfo::IsStarted
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
ms.openlocfilehash: 1dfeb6101a6b8e33ab2fe35f318087d7f1834b6a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95714891"
---
# <a name="iclrruntimeinfoisstarted-method"></a>Метод ICLRRuntimeInfo::IsStarted

Указывает, была ли запущена среда выполнения (т. е. был ли вызван [метод ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) и он был успешно выполнен).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a>Параметры  

 `pbStarted`  
 [out] `true` значение, если среда выполнения запущена; в противном случае — `false` .  
  
 `pdwStartupFlags`  
 заполняет Возвращает флаги, которые использовались для запуска среды выполнения.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_NOTIMPL|Версия среды CLR предшествует версии CLR в .NET Framework 4.|  
  
## <a name="remarks"></a>Комментарии  

 Этот метод не работает с версиями CLR, предшествующими версии CLR в .NET Framework 4.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

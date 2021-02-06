---
description: 'Дополнительные сведения о методе ICLRRuntimeInfo:: GetProcAddress'
title: Метод ICLRRuntimeInfo::GetProcAddress
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
ms.openlocfilehash: 1e5d08ed118930418106b28541b4081d6acad927
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637148"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a>Метод ICLRRuntimeInfo::GetProcAddress

Возвращает адрес указанной функции, которая была экспортирована из среды CLR, связанной с этим интерфейсом.  
  
 Этот метод заменяет функцию [жетреалпрокаддресс](getrealprocaddress-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a>Параметры  

 `pszProcName`  
 окне Имя экспортированной функции.  
  
 `ppProc`  
 заполняет Адрес экспортированной функции.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|`pszProcName` или `ppProc` равно null.|  
|CLR_E_SHIM_RUNTIMEEXPORT|Указанная функция не является экспортированной функцией.|  
  
## <a name="remarks"></a>Remarks  

 Этот метод приводит к тому, что среда CLR загружается, но не инициализируется.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

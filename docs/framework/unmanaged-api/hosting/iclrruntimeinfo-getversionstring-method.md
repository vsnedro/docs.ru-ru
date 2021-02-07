---
description: 'Дополнительные сведения: метод ICLRRuntimeInfo:: GetVersionString'
title: Метод ICLRRuntimeInfo::GetVersionString
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
ms.openlocfilehash: 1c7603f4e9bb1142c415ba9da7a05a52d2d5e776
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753878"
---
# <a name="iclrruntimeinfogetversionstring-method"></a>Метод ICLRRuntimeInfo::GetVersionString

Возвращает сведения о версии среды CLR, связанные с заданным интерфейсом [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) .  
  
 Этот метод заменяет следующие функции:  
  
- [GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md)  
  
- [жетрекуестедрунтимеверсион](getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a>Параметры  

 `pwzBuffer`  
 заполняет Версия компиляции платформа .NET Framework в формате "v *A*. *B*[.*X*] ". *A*, *B* и *X* — это десятичные числа, соответствующие основной версии, дополнительной версии и номеру сборки. *X* является необязательным. Если значение *X* отсутствует, конечная точка отсутствует.  
  
> [!NOTE]
> Этот параметр должен соответствовать имени каталога для платформа .NET Framework версии, как показано в разделе К:\виндовс\микрософт.нет\фрамеворк.  
  
 Примеры значений: "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" и "v 4.0. *x*", где *x* зависит от установленного номера сборки. Обратите внимание, что префикс "v" является обязательным.  
  
 `pchBuffer`  
 [вход, выход] Указывает размер `pwzBuffer` во избежание переполнения буфера. Если `pwzBuffer` имеет значение `null` , функция `pchBuffer` возвращает требуемый размер, `pwzBuffer` чтобы разрешить предварительное выделение.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|`pwzBuffer` или `pchBuffer` равно null.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Размещение](index.md)

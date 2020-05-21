---
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
ms.openlocfilehash: ccf48b6aea25bd602b55727c2e5958811702f6bf
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762582"
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
 заполняет Версия компиляции .NET Framework в формате "v*A*. *B*[.* X*] ". *A*, *B*и *X* — это десятичные числа, соответствующие основной версии, дополнительной версии и номеру сборки. *X* является необязательным. Если значение *X* отсутствует, конечная точка отсутствует.  
  
> [!NOTE]
> Этот параметр должен соответствовать имени каталога для .NET Framework версии, как показано в разделе К:\виндовс\микрософт.нет\фрамеворк.  
  
 Примеры значений: "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" и "v 4.0. *x*", где *x* зависит от установленного номера сборки. Обратите внимание, что префикс "v" является обязательным.  
  
 `pchBuffer`  
 [вход, выход] Указывает размер `pwzBuffer` во избежание переполнения буфера. Если `pwzBuffer` имеет значение `null` , функция `pchBuffer` возвращает требуемый размер, `pwzBuffer` чтобы разрешить предварительное выделение.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_POINTER|`pwzBuffer` или `pchBuffer` равно null.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRRuntimeInfo](iclrruntimeinfo-interface.md)
- [Интерфейсы размещения](hosting-interfaces.md)
- [Интерфейсы размещения CLR, добавленные в версиях .NET Framework 4 и 4.5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [Размещение](index.md)

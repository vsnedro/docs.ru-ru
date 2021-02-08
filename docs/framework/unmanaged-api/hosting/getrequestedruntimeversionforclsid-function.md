---
description: Дополнительные сведения о функции Жетрекуестедрунтимеверсионфорклсид
title: Функция GetRequestedRuntimeVersionForCLSID
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersionForCLSID
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersionForCLSID
helpviewer_keywords:
- GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type:
- apiref
ms.openlocfilehash: 10fdc947181d3f1fa12b33f11cf31b68fc4285cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785267"
---
# <a name="getrequestedruntimeversionforclsid-function"></a>Функция GetRequestedRuntimeVersionForCLSID

Возвращает соответствующую информацию о версии среды CLR для класса с указанным `CLSID` .  
  
 Эта функция является устаревшей в платформа .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,
    [out]  LPWSTR     pVersion,
    [in]  DWORD      cchBuffer,
    [out] DWORD*     dwLength,
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `rclsid`  
 окне  `CLSID` Компонента.  
  
 `pVersion`  
 заполняет  Буфер, содержащий строку номера версии после успешного завершения.  
  
 `cchBuffer`  
 окне  Размер буфера в расширенных символах `pVersion` .  
  
 `dwLength`  
 заполняет Длина возвращенного буфера в байтах.  
  
 `dwResolutionFlags`  
 окне  Одно из значений CLSID_RESOLUTION_FLAGS. Поддерживаются следующие значения.  
  
- CLSID_RESOLUTION_DEFAULT: (0x0) указывает, что следует использовать режим взаимодействия по умолчанию.  
  
- CLSID_RESOLUTION_REGISTERED: (0x1) указывает, что необходимо выполнять поиск в реестре и применять политику оболочки совместимости.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание:|  
|-------------|-----------------|  
|S_OK|Функция возвращена успешно.|  
|E_INVALIDARG|Один из параметров имеет недопустимый тип или формат.|  
|ERROR_INSUFFICIENT_BUFFER|`pVersion`Буфер недостаточно велик для размещения всей строки версии.|  
|REGDB_E_CLASSNOTREG|Отсутствует класс, зарегистрированный в указанном классе `CLSID` .|  
|E_POINTER|`dwLength` параметр имеет значение null или `cchBuffer` достаточно велик для хранения строки версии, но `pVersion` имеет значение null.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

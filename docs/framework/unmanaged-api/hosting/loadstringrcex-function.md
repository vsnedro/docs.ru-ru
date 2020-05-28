---
title: Функция LoadStringRCEx
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
ms.openlocfilehash: a05cbe985c2cfebb67756fdfb54398b36e87f441
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008522"
---
# <a name="loadstringrcex-function"></a>Функция LoadStringRCEx
Преобразует значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.  
  
 Эта функция является устаревшей в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `lcid`  
 окне Идентификатор языка и региональных параметров. Pass-1 для `lcid` для использования языка и региональных параметров по умолчанию.  
  
 `iResourceID`  
 [in] Значение HRESULT.  
  
 `szBuffer`  
 заполняет Буфер, содержащий сообщение об ошибке после успешного завершения.  
  
 `iMax`  
 окне Размер буфера сообщений об ошибках.  
  
 `bQuiet`  
 окне Игнорируют.  
  
 `pcwchUsed`  
 заполняет Указатель на длину сообщения об ошибке.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError. h, а также следующие значения.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|`szBuffer`имеет значение null или `iMax` равно нулю (0).|  
  
## <a name="remarks"></a>Примечания  
 Если метод не завершается успешно, `szBuffer` содержит пустую строку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [Функция LoadStringRC](loadstringrc-function.md)
- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

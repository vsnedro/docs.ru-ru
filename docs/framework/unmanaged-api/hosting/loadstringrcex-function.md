---
description: Дополнительные сведения о функции Лоадстрингрцекс
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
ms.openlocfilehash: d3fe4b97014e5093dd8d209a5e27bac4ed7b879f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679924"
---
# <a name="loadstringrcex-function"></a>Функция LoadStringRCEx

Преобразует значение HRESULT в соответствующее сообщение об ошибке для указанного языка и региональных параметров.  
  
 Эта функция является устаревшей в платформа .NET Framework 4.  
  
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
|E_INVALIDARG|`szBuffer` имеет значение null или `iMax` равно нулю (0).|  
  
## <a name="remarks"></a>Remarks  

 Если метод не завершается успешно, `szBuffer` содержит пустую строку.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [Функция LoadStringRC](loadstringrc-function.md)
- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

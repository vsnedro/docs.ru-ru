---
title: Функция LoadStringRC
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
ms.openlocfilehash: 8bd0292ddf22453f8892ed8bddd10c2144877097
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008523"
---
# <a name="loadstringrc-function"></a>Функция LoadStringRC
Преобразует значение HRESULT в сообщение об ошибке с помощью языка и региональных параметров по умолчанию текущего потока.  
  
 Эта функция является устаревшей в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `iResourceID`  
 [in] Значение HRESULT.  
  
 `szBuffer`  
 заполняет Буфер, содержащий сообщение об ошибке после успешного завершения.  
  
 `iMax`  
 окне Размер буфера сообщений об ошибках.  
  
 `bQuiet`  
 окне Игнорируют.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|`szBuffer`имеет значение null или `iMax` равно нулю (0).|  
  
## <a name="remarks"></a>Примечания  
 Если метод не завершается успешно, `szBuffer` содержит пустую строку.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll и mscorwks. dll. Используйте библиотеку MSCorEE. dll вместо Mscorwks. dll, чтобы обеспечить правильную версию .NET Framework.  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Функция LoadStringRCEx](loadstringrcex-function.md)
- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

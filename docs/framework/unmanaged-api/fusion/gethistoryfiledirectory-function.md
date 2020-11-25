---
title: Функция GetHistoryFileDirectory
ms.date: 03/30/2017
api_name:
- GetHistoryFileDirectory
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- GetHistoryFileDirectory
helpviewer_keywords:
- GetHistoryFileDirectory function [.NET Framework fusion]
ms.assetid: 93232222-926e-42ac-b85d-8a6d33977672
topic_type:
- apiref
ms.openlocfilehash: 484adf288356b9955fe0cac0bb30002ec1f012d3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724442"
---
# <a name="gethistoryfiledirectory-function"></a>Функция GetHistoryFileDirectory

Возвращает путь к каталогу журнала приложения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHistoryFileDirectory (  
    [in]      LPWSTR      wzDir,  
    [in,out]  LPCWSTR  *pdwsize,  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `wzDir`  
 заполняет Буфер для хранения пути к каталогу журнала приложения.  
  
 `pdwSize`  
 [вход, выход] Длина буфера.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает коды стандартных ошибок COM, как определено в файле WinError. h, а также следующие значения.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|E_INVALIDARG|`wzDir` или `pdwSize` имеет значение null, или строка версии неверна.|  
  
## <a name="remarks"></a>Комментарии  

 При успешном завершении `pdwSize` аргументу присваивается длина строки пути.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Библиотека:** Fusion.dll и Mscorwks.dll. Используйте Fusion.dll вместо Mscorwks.dll, чтобы убедиться в правильности целевой версии .NET Framework.  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Функция CreateHistoryReader](createhistoryreader-function.md)
- [Функция NukeDownloadedCache](nukedownloadedcache-function.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)

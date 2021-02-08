---
description: Дополнительные сведения о функции NukeDownloadedCache
title: Функция NukeDownloadedCache
ms.date: 03/30/2017
api_name:
- NukeDownloadedCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- NukeDownloadedCache
helpviewer_keywords:
- NukeDownloadedCache function [.NET Framework fusion]
ms.assetid: fac2b1c6-6fa3-4818-805b-b63972024c86
topic_type:
- apiref
ms.openlocfilehash: 2239473b8e6e43a539b0507c8255d40f87e72043
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800036"
---
# <a name="nukedownloadedcache-function"></a>Функция NukeDownloadedCache

Удаляет кэш загрузки среды CLR.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT NukeDownloadedCache();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает стандартные коды ошибок COM, как определено в файле WinError. h.  
  
## <a name="remarks"></a>Remarks  

 Кэш загрузки среды CLR — это область, в которой хранятся сборки со строгими именами, загружаемые из URL-адреса для возможного повторного использования.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Библиотека:** Fusion.dll и Mscorwks.dll. Используйте Fusion.dll вместо Mscorwks.dll, чтобы убедиться в правильности целевой версии платформа .NET Framework.  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция CreateHistoryReader](createhistoryreader-function.md)
- [Функция GetHistoryFileDirectory](gethistoryfiledirectory-function.md)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)

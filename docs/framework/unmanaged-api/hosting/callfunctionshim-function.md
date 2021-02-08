---
description: Дополнительные сведения о функции Каллфунктионшим
title: Функция CallFunctionShim
ms.date: 03/30/2017
api_name:
- CallFunctionShim
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CallFunctionShim
helpviewer_keywords:
- CallfunctionShim function [.NET Framework hosting]
ms.assetid: 37118465-ddf3-41f0-bf27-335b72777e63
topic_type:
- apiref
ms.openlocfilehash: 7ddd16a06005011adcf41190929fd62f4132f14d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799958"
---
# <a name="callfunctionshim-function"></a>Функция CallFunctionShim

Вызывает функцию с указанным именем и параметрами в указанной библиотеке.  
  
 Эта функция является устаревшей в платформа .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CallFunctionShim (  
    [in] LPCWSTR     szDllName,  
    [in] LPCSTR      szFunctionName,  
    [in] LPVOID      lpvArgument1,  
    [in] LPVOID      lpvArgument2,  
    [in] LPCWSTR     szVersion,  
    [in] LPVOID      pvReserved  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `szDllName`  
 окне Имя библиотеки, содержащей функцию.  
  
 `szFunctionName`  
 окне Имя функции.  
  
 `lpvArgument1`  
 окне Первый аргумент для передачи в функцию.  
  
 `lpvArgument2`  
 окне Второй аргумент для передачи в функцию.  
  
 `szVersion`  
 окне Версия библиотеки, которая содержит функцию.  
  
 `pvReserved`  
 [in] Зарезервирован для будущего использования. В этом параметре следует передать ноль.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

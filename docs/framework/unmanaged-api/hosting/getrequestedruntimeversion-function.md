---
description: Дополнительные сведения о функции Жетрекуестедрунтимеверсион
title: Функция GetRequestedRuntimeVersion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
ms.openlocfilehash: 836cc4b875ddc427c6779950f5b68d2df8b6ef75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785280"
---
# <a name="getrequestedruntimeversion-function"></a>Функция GetRequestedRuntimeVersion

Возвращает номер версии общеязыковой среды выполнения (CLR), запрошенной указанным приложением. Если эта версия не установлена, возвращает последнюю версию, установленную до запрошенной версии.  
  
 Эта функция является устаревшей в платформа .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pExe`  
 окне Имя приложения.  
  
 `pVersion`  
 заполняет Буфер, содержащий строку номера версии после успешного завершения.  
  
 `cchBuffer`  
 окне Длина буфера версии.  
  
 `pdwLength`  
 заполняет Указатель на длину строки номера версии.  
  
## <a name="return-value"></a>Возвращаемое значение  

 Этот метод возвращает коды стандартных ошибок модели COM, как определено в файле WinError. h, в дополнение к следующим значениям.  
  
|Код возврата|Описание|  
|-----------------|-----------------|  
|S_OK|Метод завершился успешно.|  
|ERROR_INSUFFICIENT_BUFFER|Буфер версии недостаточно велик для хранения строки версии.|  
|E_POINTER|Параметр `pdwLength` имеет значение null.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция GetRequestedRuntimeInfo](getrequestedruntimeinfo-function.md)
- [Функция GetVersionFromProcess](getversionfromprocess-function.md)
- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

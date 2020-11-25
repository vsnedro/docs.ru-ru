---
title: Функция GetAssemblyIdentityFromFile
ms.date: 03/30/2017
api_name:
- GetAssemblyIdentityFromFile
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyIdentityFromFile
helpviewer_keywords:
- GetAssemblyIdentityFromFile function [.NET Framework fusion]
ms.assetid: 2c32da53-76c7-4048-84d0-d05207333004
topic_type:
- apiref
ms.openlocfilehash: 9580dd3bc5a7279549e8deadac95d35a33da74f8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724485"
---
# <a name="getassemblyidentityfromfile-function"></a>Функция GetAssemblyIdentityFromFile

Возвращает указатель на `IUnknown` объект с указанным `IID` в сборке по указанному пути к файлу.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetAssemblyIdentityFromFile (  
    [in]  LPCWSTR   pwzFilePath,  
    [in]  REFIID    riid,  
    [out] IUnknown  **ppIdentity  
 );  
```  
  
## <a name="parameters"></a>Параметры  

 `pwzFilePath`  
 окне Допустимый путь к запрошенной сборке.  
  
 `riid`  
 окне `IID` Возвращаемый интерфейс.  
  
 `ppIdentity`  
 заполняет Возвращаемый указатель интерфейса.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [IUnknown](/cpp/atl/iunknown)
- [Глобальные статические функции Fusion](fusion-global-static-functions.md)

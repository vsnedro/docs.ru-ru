---
title: Функция GetFileVersion
ms.date: 03/30/2017
api_name:
- GetFileVersion
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetFileVersion
helpviewer_keywords:
- GetFileVersion function [.NET Framework hosting]
ms.assetid: b3222c85-da88-4485-97d7-3a6ee3e8d358
topic_type:
- apiref
ms.openlocfilehash: 2dd004a44b20d48dafc72711ac23abcb55739224
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617204"
---
# <a name="getfileversion-function"></a>Функция GetFileVersion
Возвращает сведения о версии среды CLR указанного файла, используя указанный буфер.  
  
 Эта функция является устаревшей в .NET Framework 4.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetFileVersion (  
    [in]  LPCWSTR      szFilename,
    [in, out] LPWSTR   szBuffer,
    [in]  DWORD        cchBuffer,
    [out] DWORD        *dwLength  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `szFilename`  
 окне Путь к файлу, который необходимо проверить.  
  
 `szBuffer`  
 [вход, выход] Буфер, выделенный для возвращаемой информации о версии.  
  
 `cchBuffer`  
 окне Размер (в расширенных символах) `szBuffer` .  
  
 `dwLength`  
 заполняет Размер возвращаемого объекта (в байтах) `szBuffer` .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Дополнительно

- [Устаревшие функции размещения CLR](deprecated-clr-hosting-functions.md)

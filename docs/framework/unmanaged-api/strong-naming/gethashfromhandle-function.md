---
title: Функция GetHashFromHandle
ms.date: 03/30/2017
api_name:
- GetHashFromHandle
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromHandle
helpviewer_keywords:
- GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type:
- apiref
ms.openlocfilehash: 904dcb707e704cfec2dba4e6587f7e3acaf7b538
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732337"
---
# <a name="gethashfromhandle-function"></a>Функция GetHashFromHandle

Создает хэш содержимого файла с заданным дескриптором файла с помощью указанного хэш-алгоритма.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `hFile`  
 окне Описатель файла для хэширования.  
  
 `piHashAlg`  
 [вход, выход] Константа, указывающая хэш-алгоритм. Используйте нуль для алгоритма по умолчанию.  
  
 `pbHash`  
 заполняет Возвращаемый буфер хэша.  
  
 `cchHash`  
 окне Запрошенный максимальный размер `pbHash` .  
  
 `pchHash`  
 заполняет Размер возвращаемого объекта (в байтах) `pbHash` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetHashFromHandle](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)

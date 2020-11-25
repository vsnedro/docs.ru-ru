---
title: Функция GetHashFromFile
ms.date: 03/30/2017
api_name:
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
ms.openlocfilehash: ee9f9cd9a9f35c6c54497ad382bb6f9817d186bd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732376"
---
# <a name="gethashfromfile-function"></a>Функция GetHashFromFile

Создает хэш содержимого указанного файла.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE     *pbHash,
    [in]  DWORD    cchHash,
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `szFilePath`  
 окне Имя файла для хэширования.  
  
 `piHashAlg`  
 [вход, выход] Алгоритм, используемый при формировании хэша. Допустимыми являются алгоритмы, определяемые интерфейсом Win32 CryptoAPI. Если параметр `piHashAlg` имеет значение 0, используется алгоритм по умолчанию CALG_SHA-1.  
  
 `pbHash`  
 заполняет Массив байтов, содержащий созданный хэш.  
  
 `cchHash`  
 окне Максимальный размер буфера, `pbHash` на который указывает.  
  
 `pchHash`  
 заполняет Размер возвращаемого объекта (в байтах) `pbHash` .  
  
## <a name="remarks"></a>Комментарии  

 Эта функция аналогична [GetHashFromFileW](gethashfromfilew-function.md), за исключением того, что спецификация имени файла является ANSI, а не Unicode.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md)
- [Метод GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)

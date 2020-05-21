---
title: Метод ICLRStrongName::GetHashFromFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
ms.openlocfilehash: e4a5f6440a016176cf06704b342c173b29748e78
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762114"
---
# <a name="iclrstrongnamegethashfromfile-method"></a>Метод ICLRStrongName::GetHashFromFile
Создает хэш содержимого указанного файла.  
  
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
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Комментарии  
 Этот метод аналогичен методу [метод iclrstrongname:: GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md) , за исключением того, что спецификация имени файла является ANSI, а не Unicode.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md)
- [Интерфейс ICLRStrongName](iclrstrongname-interface.md)

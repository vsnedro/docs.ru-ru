---
description: 'Дополнительные сведения о методе: метод iclrstrongname:: GetHashFromFileW'
title: Метод ICLRStrongName::GetHashFromFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 6145a044f490ef3827de6db8d84d16222306642d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636979"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a>Метод ICLRStrongName::GetHashFromFileW

Создает хэш содержимого файла, указанного строкой Юникода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHashFromFileW (
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);
```  
  
## <a name="parameters"></a>Параметры  

 `wszFilePath`  
 окне Имя файла в Юникоде для хэширования.  
  
 `piHashAlg`  
 [вход, выход] Алгоритм, используемый при формировании хэша. Допустимыми являются алгоритмы, определяемые интерфейсом Win32 CryptoAPI. Если параметр `piHashAlg` имеет значение 0, используется алгоритм по умолчанию CALG_SHA-1.  
  
 `pbHash`  
 заполняет Массив байтов, содержащий созданный хэш.  
  
 `cchHash`  
 окне Максимальный размер буфера, на который указывает `pbHash` .  
  
 `pchHash`  
 заполняет Размер (в байтах) `pbHash` .  
  
## <a name="return-value"></a>Возвращаемое значение  

 `S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Remarks  

 Этот метод аналогичен методу [метод iclrstrongname:: GetHashFromFile](iclrstrongname-gethashfromfile-method.md) , за исключением того, что спецификация имени файла имеет кодировку Unicode, а не ANSI.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetHashFromFile](iclrstrongname-gethashfromfile-method.md)
- [Интерфейс ICLRStrongName](iclrstrongname-interface.md)

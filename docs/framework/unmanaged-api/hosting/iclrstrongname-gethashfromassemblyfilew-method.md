---
description: 'Дополнительные сведения о методе: метод iclrstrongname:: GetHashFromAssemblyFileW'
title: Метод ICLRStrongName::GetHashFromAssemblyFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFileW method [.NET Framework hosting]
- GetHashFromAssemblyFileW method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5d0b44a2-5a14-44a2-9a0e-e8682fd4e106
topic_type:
- apiref
ms.openlocfilehash: 27123ed8217d49765fe3fd7c19efc92f4e770722
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637083"
---
# <a name="iclrstrongnamegethashfromassemblyfilew-method"></a>Метод ICLRStrongName::GetHashFromAssemblyFileW

Создает хэш содержимого файла, указанного строкой Юникода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `wszFilePath`  
 окне Путь к файлу для хэширования. Этот параметр должен быть строкой в Юникоде.  
  
 `piHashAlg`  
 [вход, выход] Константа, указывающая хэш-алгоритм. Для алгоритма хэширования по умолчанию используется нуль.  
  
 `pbHash`  
 заполняет Возвращаемый буфер хэша.  
  
 `cchHash`  
 окне Запрошенный максимальный размер `pbHash` .  
  
 `pchHash`  
 заполняет Возвращаемый размер (в байтах) для `pbHash` .  
  
## <a name="return-value"></a>Возвращаемое значение  

 `S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод GetHashFromAssemblyFile](iclrstrongname-gethashfromassemblyfile-method.md)
- [Интерфейс ICLRStrongName](iclrstrongname-interface.md)

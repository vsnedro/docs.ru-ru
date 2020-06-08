---
title: Метод ICLRStrongName::StrongNameSignatureVerificationEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
ms.openlocfilehash: 5bd985a6870ae6f4cc2302b6a11e8e139180d839
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503995"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a>Метод ICLRStrongName::StrongNameSignatureVerificationEx
Возвращает значение, указывающее, содержит ли манифест сборки по указанному пути подпись строгого имени.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszFilePath`  
 окне Путь к переносимому исполняемому файлу (exe или DLL) для проверяемой сборки.  
  
 `fForceVerification`  
 [входные] `true` для выполнения проверки, даже если необходимо переопределить параметры реестра; в противном случае — `false` .  
  
 `pfWasVerified`  
 [out] `true` значение, если подпись строгого имени проверена; в противном случае — `false` . `pfWasVerified`также имеет значение, `false` Если проверка прошла успешно из-за параметров реестра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`значение, если проверка прошла успешно; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Примечания  
 Метод [метод iclrstrongname:: StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) предоставляет такую возможность, как метод [метод iclrstrongname:: StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md) . Однако второй входной параметр и выходной параметр для [метод iclrstrongname:: StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md) имеют тип, `BOOLEAN` а не `DWORD` .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md)
- [Интерфейс ICLRStrongName](iclrstrongname-interface.md)

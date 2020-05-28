---
title: Метод StrongNameSignatureVerificationEx2
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
ms.openlocfilehash: 5e6f77b9b5da061a75d23d7f3f7b673754b62afd
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006372"
---
# <a name="strongnamesignatureverificationex2-method"></a>Метод StrongNameSignatureVerificationEx2
Проверяет подпись сборки со строгим именем и обеспечивает сопоставление ключа ECMA с реальным ключом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `wszFilePath`  
 окне Путь к переносимому исполняемому файлу (exe или DLL) для проверяемой сборки.  
  
 `fForceVerification`  
 [входные] `true` для выполнения проверки, даже если необходимо переопределить параметры реестра; в противном случае — `false` .  
  
 `pbEcmaPublicKey`  
 окне Указатель на сопоставление открытого ключа ECMA с реальным ключом, используемым для проверки.  
  
 `cbEcmaPublicKey`  
 окне Длина действительного открытого ключа ECMA.  
  
 `pfWasVerified`  
 [out] `true` значение, если подпись строгого имени проверена; в противном случае — `false` . Этот параметр также устанавливается в значение, `false` Если проверка прошла успешно из-за параметров реестра.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`значение, если проверка прошла успешно; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Метод StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md)
- [Метод StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md)
- [Интерфейс ICLRStrongName](iclrstrongname-interface.md)

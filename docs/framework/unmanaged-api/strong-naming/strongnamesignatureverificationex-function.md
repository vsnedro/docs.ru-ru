---
title: Функция StrongNameSignatureVerificationEx
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx function [.NET Framework strong naming]
ms.assetid: cfe4b634-18bf-44b8-9773-d94fb7e8a480
topic_type:
- apiref
ms.openlocfilehash: 27417c379411e242c48d6d9b0c99de833f7ede8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719272"
---
# <a name="strongnamesignatureverificationex-function"></a>Функция StrongNameSignatureVerificationEx

Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameSignatureVerificationEx (  
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
 [out] `true` значение, если подпись строгого имени проверена; в противном случае — `false` . `pfWasVerified` также имеет значение, `false` Если проверка прошла успешно из-за параметров реестра.  
  
## <a name="return-value"></a>Возвращаемое значение  

 `true` значение, если проверка прошла успешно; в противном случае — `false` .  
  
## <a name="remarks"></a>Комментарии  

 `StrongNameSignatureVerificationEx` предоставляет такую возможность, как функция [StrongNameSignatureVerification](strongnamesignatureverification-function.md) . Однако второй входной параметр и выходной параметр для `StrongNameSignatureVerificationEx` имеют тип, `BOOLEAN` а не `DWORD` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в mscoree.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод StrongNameSignatureVerificationEx](../hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [Метод StrongNameSignatureVerification](../hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)

---
title: Функция StrongNameSignatureSize
ms.date: 03/30/2017
api_name:
- StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureSize
helpviewer_keywords:
- StrongNameSignatureSize function [.NET Framework strong naming]
ms.assetid: 4fde4cd0-f53e-4411-a2fe-fc5c54472f95
topic_type:
- apiref
ms.openlocfilehash: 6a2b3afe66f1eaa358c5f80de50f14ceb730048b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708482"
---
# <a name="strongnamesignaturesize-function"></a>Функция StrongNameSignatureSize

Возвращает размер подписи строгого имени. `StrongNameSignatureSize` обычно используется компиляторами для определения объема пространства, резервируемого в файле при создании сборки с отложенной подписью.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameSignatureSize (
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,
    [in]  DWORD  *pcbSize  
);
```  
  
## <a name="parameters"></a>Параметры  

 `pbPublicKeyBlob`  
 окне Структура типа [публиккэйблоб](publickeyblob-structure.md) , содержащая открытую часть пары ключей, используемую для создания подписи строгого имени.  
  
 `cbPublicKeyBlob`  
 окне Размер (в байтах) `pbPublicKeyBlob` .  
  
 `pcbSize`  
 окне Число байтов, необходимое для хранения подписи строгого имени.  
  
## <a name="return-value"></a>Возвращаемое значение  

 `true` При успешном завершении; в противном случае — `false` .  
  
## <a name="remarks"></a>Комментарии  

 Если `StrongNameSignatureSize` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)

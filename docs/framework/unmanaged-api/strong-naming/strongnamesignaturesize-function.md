---
description: Дополнительные сведения о функции StrongNameSignatureSize
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
ms.openlocfilehash: b3f22a6a4d5455af4dd17cb75edfd18befed7de3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670532"
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
  
## <a name="remarks"></a>Remarks  

 Если `StrongNameSignatureSize` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameSignatureSize](../hosting/iclrstrongname-strongnamesignaturesize-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)

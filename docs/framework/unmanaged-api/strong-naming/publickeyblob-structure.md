---
title: Структура PublicKeyBlob
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
ms.openlocfilehash: 42cd3cc22fbbb8eb3d5ac44544fce36650b6461f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705934"
---
# <a name="publickeyblob-structure"></a>Структура PublicKeyBlob

Представляет в двоичном формате открытый ключ пары открытого и закрытого ключей.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`SigAlgId`|Идентификатор для алгоритма подписи (типа `ALG_ID` , как определено в винкрипт. h) открытого ключа.|  
|`HashAlgId`|Идентификатор для хэш-алгоритма (типа `ALG_ID` , как определено в винкрипт. h) открытого ключа.|  
|`cbPublicKey`|Длина ключа в байтах.|  
|`PublicKey`|Массив байтов переменной длины, который содержит значение ключа в формате, возвращенном CryptoAPI.|  
  
## <a name="remarks"></a>Комментарии  

 `PublicKeyBlob`Структура используется [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)и другими функциями строгого имени для представления открытого ключа пары открытого и закрытого ключей.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Функция StrongNameGetPublicKey](strongnamegetpublickey-function.md)
- [Функция StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)

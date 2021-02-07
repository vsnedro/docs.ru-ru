---
description: 'Дополнительные сведения о: структура Публиккэйблоб'
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
ms.openlocfilehash: 94c1ea3d5a41bbb8941658e87f97cd6d6336187a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736494"
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
  
## <a name="remarks"></a>Remarks  

 `PublicKeyBlob`Структура используется [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)и другими функциями строгого имени для представления открытого ключа пары открытого и закрытого ключей.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Функция StrongNameGetPublicKey](strongnamegetpublickey-function.md)
- [Функция StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)

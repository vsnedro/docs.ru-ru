---
description: Дополнительные сведения о функции StrongNameTokenFromPublicKey
title: Функция StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
ms.openlocfilehash: f978c9b2727db4b293b9c92a8789fbf9ba749d41
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636288"
---
# <a name="strongnametokenfrompublickey-function"></a>Функция StrongNameTokenFromPublicKey

Получает маркер, представляющий открытый ключ. Маркер строгого имени — это сокращенная форма открытого ключа.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pbPublicKeyBlob`  
 окне Структура типа [публиккэйблоб](publickeyblob-structure.md) , содержащая открытую часть пары ключей, используемую для создания подписи строгого имени.  
  
 `cbPublicKeyBlob`  
 окне Размер (в байтах) `pbPublicKeyBlob` .  
  
 `ppbStrongNameToken`  
 заполняет Маркер строгого имени, соответствующий переданному ключу `pbPublicKeyBlob` . Среда CLR выделяет память, в которую возвращается маркер. Вызывающий объект должен освободить эту память с помощью функции [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .  
  
 `pcbStrongNameToken`  
 заполняет Размер возвращенного маркера строгого имени в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  

 `true` При успешном завершении; в противном случае — `false` .  
  
## <a name="remarks"></a>Remarks  

 Маркер строгого имени — это сокращенная форма открытого ключа, используемая для экономии места при хранении ключевых сведений в метаданных. В частности, маркеры строгого имени используются в ссылках на сборки для ссылки на зависимую сборку.  
  
 Если `StrongNameTokenFromPublicKey` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в mscoree.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Метод StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [Структура PublicKeyBlob](publickeyblob-structure.md)

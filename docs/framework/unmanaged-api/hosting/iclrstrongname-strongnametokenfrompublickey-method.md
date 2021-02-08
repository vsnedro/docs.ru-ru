---
description: 'Дополнительные сведения о методе: метод iclrstrongname:: StrongNameTokenFromPublicKey'
title: Метод ICLRStrongName::StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: de245b151e5ca016a00793a8901c0fd990a3f804
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789749"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a>Метод ICLRStrongName::StrongNameTokenFromPublicKey

Возвращает маркер, представляющий открытый ключ. Маркер строгого имени — это сокращенная форма открытого ключа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pbPublicKeyBlob`  
 окне Структура типа [публиккэйблоб](../strong-naming/publickeyblob-structure.md) , содержащая открытую часть пары ключей, используемую для создания подписи строгого имени.  
  
 `cbPublicKeyBlob`  
 окне Размер (в байтах) `pbPublicKeyBlob` .  
  
 `ppbStrongNameToken`  
 заполняет Маркер строгого имени, соответствующий переданному ключу `pbPublicKeyBlob` . Среда CLR выделяет память, в которую возвращается маркер. Вызывающий объект должен освободить эту память с помощью метода [метод iclrstrongname:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) .  
  
 `pcbStrongNameToken`  
 заполняет Размер возвращенного маркера строгого имени в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  

 `S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Remarks  

 Маркер строгого имени — это сокращенная форма открытого ключа, используемая для экономии места при хранении ключевых сведений в метаданных. В частности, маркеры строгого имени используются в ссылках на сборки для ссылки на зависимую сборку.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в mscoree.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md)
- [Структура PublicKeyBlob](../strong-naming/publickeyblob-structure.md)
- [Интерфейс ICLRStrongName](iclrstrongname-interface.md)

---
title: Метод ICLRStrongName::StrongNameGetPublicKey
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
ms.openlocfilehash: 5bd314b2b63474d2a1d159f74564e2d4ca13aef6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725551"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a>Метод ICLRStrongName::StrongNameGetPublicKey

Возвращает открытый ключ из пары открытого и закрытого ключей. Пара ключей может быть задана как имя контейнера ключей в поставщике служб шифрования (CSP) или как необработанная коллекция байтов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `szKeyContainer`  
 окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей. Если `pbKeyBlob` значение равно null, `szKeyContainer` необходимо указать допустимый контейнер в CSP. В этом случае метод [метод iclrstrongname:: StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md) извлекает открытый ключ из пары ключей, хранящейся в контейнере.  
  
 Если значение не равно `pbKeyBlob` null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).  
  
 Ключи должны состоять из 1024-разрядных ключей подписывания Ривест-Шамир-Адельман (RSA). В настоящее время не поддерживаются никакие другие типы ключей.  
  
 `pbKeyBlob`  
 окне Указатель на пару открытого и закрытого ключей. Эта пара имеет формат, созданный `CryptExportKey` функцией Win32. Если аргумент `pbKeyBlob` имеет значение null, предполагается, что контейнер ключей, заданный параметром, `szKeyContainer` содержит пару ключей.  
  
 `cbKeyBlob`  
 окне Размер (в байтах) `pbKeyBlob` .  
  
 `ppbPublicKeyBlob`  
 заполняет Возвращенный большой двоичный объект открытого ключа. `ppbPublicKeyBlob`Параметр выделяется средой CLR и возвращается вызывающему объекту. Вызывающий объект должен освободить память с помощью метода [метод iclrstrongname:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) .  
  
 `pcbPublicKeyBlob`  
 заполняет Размер возвращенного большого двоичного объекта открытого ключа.  
  
## <a name="return-value"></a>Возвращаемое значение  

 `S_OK` значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Комментарии  

 Открытый ключ содержится в структуре [публиккэйблоб](../strong-naming/publickeyblob-structure.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md)
- [Структура PublicKeyBlob](../strong-naming/publickeyblob-structure.md)
- [Интерфейс ICLRStrongName](iclrstrongname-interface.md)

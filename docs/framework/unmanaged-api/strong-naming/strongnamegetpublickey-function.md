---
title: Функция StrongNameGetPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
ms.openlocfilehash: c97cc0c1d4c022583d0823abeff998e2ed5f719e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710978"
---
# <a name="strongnamegetpublickey-function"></a>Функция StrongNameGetPublicKey

Получает открытый ключ из пары закрытого и открытого ключей. Пара ключей может быть задана как имя контейнера ключей в поставщике служб шифрования (CSP) или как необработанная коллекция байтов.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `szKeyContainer`  
 окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей. Если `pbKeyBlob` значение равно null, `szKeyContainer` необходимо указать допустимый контейнер в CSP. В этом случае `StrongNameGetPublicKey` извлекает открытый ключ из пары ключей, хранящейся в контейнере.  
  
 Если значение не равно `pbKeyBlob` null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).  
  
 Ключи должны состоять из 1024-разрядных ключей подписывания Ривест-Шамир-Адельман (RSA). В настоящее время не поддерживаются никакие другие типы ключей.  
  
 `pbKeyBlob`  
 окне Указатель на пару открытого и закрытого ключей. Эта пара имеет формат, созданный `CryptExportKey` функцией Win32. Если аргумент `pbKeyBlob` имеет значение null, предполагается, что контейнер ключей, заданный параметром, `szKeyContainer` содержит пару ключей.  
  
 `cbKeyBlob`  
 окне Размер (в байтах) `pbKeyBlob` .  
  
 `ppbPublicKeyBlob`  
 заполняет Возвращенный большой двоичный объект открытого ключа. `ppbPublicKeyBlob`Параметр выделяется средой CLR и возвращается вызывающему объекту. Вызывающий объект должен освободить память с помощью функции [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .  
  
 `pcbPublicKeyBlob`  
 заполняет Размер возвращенного большого двоичного объекта открытого ключа.  
  
## <a name="return-value"></a>Возвращаемое значение  

 `true` При успешном завершении; в противном случае — `false` .  
  
## <a name="remarks"></a>Комментарии  

 Открытый ключ содержится в структуре [публиккэйблоб](publickeyblob-structure.md) .  
  
 Если `StrongNameGetPublicKey` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Метод StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [Метод StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)
- [Структура PublicKeyBlob](publickeyblob-structure.md)

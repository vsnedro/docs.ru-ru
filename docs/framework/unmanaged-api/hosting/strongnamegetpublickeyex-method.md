---
title: Метод StrongNameGetPublicKeyEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
ms.openlocfilehash: 1904a98f254a988ce035847a4cdeede182aa07bf
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84006380"
---
# <a name="strongnamegetpublickeyex-method"></a>Метод StrongNameGetPublicKeyEx
Получает открытый ключ из пары открытого и закрытого ключей и задает алгоритм хеширования и алгоритм подписи.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pwzKeyContainer`  
 окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей. Если `pbKeyBlob` параметр имеет значение null, `szKeyContainer` необходимо указать допустимый контейнер в поставщике служб шифрования (CSP). В этом случае `StrongNameGetPublicKeyEx` метод извлекает открытый ключ из пары ключей, хранящихся в контейнере.  
  
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
  
 `uHashAlgId`  
 окне Хэш-алгоритм сборки. Список допустимых значений см. в разделе "Примечания".  
  
 `uReserved`  
 окне Зарезервировано для будущего использования; по умолчанию принимает значение null.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`значение, если метод успешно выполнен; в противном случае — значение HRESULT, указывающее на сбой (см. раздел [Общие значения HRESULT](/windows/win32/seccrypto/common-hresult-values) для списка).  
  
## <a name="remarks"></a>Примечания  
 Открытый ключ содержится в структуре [публиккэйблоб](../strong-naming/publickeyblob-structure.md) .  
  
## <a name="remarks"></a>Примечания  
 В следующей таблице показан набор допустимых значений для `uHashAlgId` параметра.  
  
|Имя|Значение|  
|----------|-----------|  
|Нет|0|  
|SHA-1|0x8004|  
|SHA-256|0x800c|  
|SHA-384|0x800d|  
|SHA-512|0x800e|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Метод StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md)
- [Структура PublicKeyBlob](../strong-naming/publickeyblob-structure.md)
- [Интерфейс ICLRStrongName](iclrstrongname-interface.md)
- [Метод StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md)

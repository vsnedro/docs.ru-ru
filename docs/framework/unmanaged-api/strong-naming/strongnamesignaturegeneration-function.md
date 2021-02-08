---
description: Дополнительные сведения о функции StrongNameSignatureGeneration
title: Функция StrongNameSignatureGeneration
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
ms.openlocfilehash: 6f5a164e73af743cdd13390c60d00d553e5e0312
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798905"
---
# <a name="strongnamesignaturegeneration-function"></a>Функция StrongNameSignatureGeneration

Создает подпись строгого имени для указанной сборки.  
  
 Эта функция является устаревшей. Используйте вместо этого метод [метод iclrstrongname:: StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `wszFilePath`  
 окне Путь к файлу, содержащему манифест сборки, для которой будет создана подпись строгого имени.  
  
 `wszKeyContainer`  
 окне Имя контейнера ключей, содержащего пару открытого и закрытого ключей.  
  
 Если `pbKeyBlob` параметр имеет значение null, `wszKeyContainer` необходимо указать допустимый контейнер в поставщике служб шифрования (CSP). В этом случае для подписания файла используется пара ключей, хранящаяся в контейнере.  
  
 Если значение не равно `pbKeyBlob` null, предполагается, что пара ключей содержится в большом двоичном объекте Key (BLOB).  
  
 Ключи должны состоять из 1024-разрядных ключей подписывания Ривест-Шамир-Адельман (RSA). В настоящее время не поддерживаются никакие другие типы ключей.  
  
 `pbKeyBlob`  
 окне Указатель на пару открытого и закрытого ключей. Эта пара имеет формат, созданный `CryptExportKey` функцией Win32. Если аргумент `pbKeyBlob` имеет значение null, предполагается, что контейнер ключей, заданный параметром, `wszKeyContainer` содержит пару ключей.  
  
 `cbKeyBlob`  
 окне Размер (в байтах) `pbKeyBlob` .  
  
 `ppbSignatureBlob`  
 заполняет Указатель на расположение, в которое среда CLR возвращает подпись. Если `ppbSignatureBlob` параметр имеет значение null, среда выполнения сохраняет подпись в файле, указанном параметром `wszFilePath` .  
  
 Если значение не равно `ppbSignatureBlob` null, среда CLR выделяет пространство, в которое возвращается подпись. Вызывающий объект должен освободить это пространство с помощью функции [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .  
  
 `pcbSignatureBlob`  
 заполняет Размер возвращенной сигнатуры в байтах.  
  
## <a name="return-value"></a>Возвращаемое значение  

 `true` При успешном завершении; в противном случае — `false` .  
  
## <a name="remarks"></a>Remarks  

 Укажите значение NULL для `wszFilePath` , чтобы вычислить размер подписи без создания подписи.  
  
 Подпись может храниться непосредственно в файле или возвращаться вызывающему объекту.  
  
 Если `StrongNameSignatureGeneration` функция не завершается успешно, вызовите функцию [стронгнамирроринфо](strongnameerrorinfo-function.md) , чтобы получить последнюю созданную ошибку.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** StrongName. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Метод StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [Метод StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [Интерфейс ICLRStrongName](../hosting/iclrstrongname-interface.md)

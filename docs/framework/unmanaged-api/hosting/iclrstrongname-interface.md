---
title: Интерфейс ICLRStrongName
ms.date: 03/30/2017
api_name:
- ICLRStrongName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName
helpviewer_keywords:
- ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 2fac66fd-6b3b-4dbd-8baf-86038bd85526
topic_type:
- apiref
ms.openlocfilehash: 04260429dd69f5ba1d6a94b6628979341d12b9e8
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762088"
---
# <a name="iclrstrongname-interface"></a>Интерфейс ICLRStrongName
Предоставляет базовые глобальные статические функции для подписи сборок со строгими именами. Все `ICLRStrongName` методы возвращают стандартные значения HRESULT com.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetHashFromAssemblyFile](iclrstrongname-gethashfromassemblyfile-method.md)|Получает хэш указанного файла сборки с помощью указанного хэш-алгоритма.|  
|[Метод GetHashFromAssemblyFileW](iclrstrongname-gethashfromassemblyfilew-method.md)|Получает хэш файла сборки, указанного строкой Юникода, с помощью указанного хэш-алгоритма.|  
|[Метод GetHashFromBlob](iclrstrongname-gethashfromblob-method.md)|Получает хэш сборки по указанному адресу памяти с помощью указанного хэш-алгоритма.|  
|[Метод GetHashFromFile](iclrstrongname-gethashfromfile-method.md)|Создает хэш содержимого указанного файла.|  
|[Метод GetHashFromFileW](iclrstrongname-gethashfromfilew-method.md)|Создает хэш содержимого файла, указанного строкой Юникода.|  
|[Метод GetHashFromHandle](iclrstrongname-gethashfromhandle-method.md)|Создает хэш содержимого файла с заданным дескриптором файла с помощью указанного хэш-алгоритма.|  
|[Метод StrongNameCompareAssemblies](iclrstrongname-strongnamecompareassemblies-method.md)|Определяет, отличаются ли две сборки только подписями строгого имени.|  
|[Метод StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)|Освобождает память, выделенную с помощью предыдущего вызова метода строгого имени, такого как [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)или [StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md).|  
|[Метод StrongNameGetBlob](iclrstrongname-strongnamegetblob-method.md)|Заполняет указанный буфер двоичным представлением исполняемого файла по указанному адресу.|  
|[Метод StrongNameGetBlobFromImage](iclrstrongname-strongnamegetblobfromimage-method.md)|Получает двоичное представление образа сборки по указанному адресу памяти.|  
|[Метод StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md)|Получает открытый ключ из пары закрытого и открытого ключей.|  
|[Метод StrongNameHashSize](iclrstrongname-strongnamehashsize-method.md)|Получает размер буфера, необходимый для хэша, с помощью указанного хэш-алгоритма.|  
|[Метод StrongNameKeyDelete](iclrstrongname-strongnamekeydelete-method.md)|Удаляет указанный контейнер ключей.|  
|[Метод StrongNameKeyGen](iclrstrongname-strongnamekeygen-method.md)|Создает пару открытого и закрытого ключей для использования строгого имени.|  
|[Метод StrongNameKeyGenEx](iclrstrongname-strongnamekeygenex-method.md)|Создает пару открытого и закрытого ключей с заданным размером для использования строгого имени.|  
|[Метод StrongNameKeyInstall](iclrstrongname-strongnamekeyinstall-method.md)|Импортирует пару открытого и закрытого ключей в контейнер.|  
|[Метод StrongNameSignatureGeneration](iclrstrongname-strongnamesignaturegeneration-method.md)|Создает подпись строгого имени для указанной сборки.|  
|[Метод StrongNameSignatureGenerationEx](iclrstrongname-strongnamesignaturegenerationex-method.md)|Создает подпись строгого имени для указанной сборки в зависимости от указанных флагов.|  
|[Метод StrongNameSignatureSize](iclrstrongname-strongnamesignaturesize-method.md)|Возвращает размер подписи строгого имени.|  
|[Метод StrongNameSignatureVerification](iclrstrongname-strongnamesignatureverification-method.md)|Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени, которая проверяется в соответствии с заданными флагами.|  
|[Метод StrongNameSignatureVerificationEx](iclrstrongname-strongnamesignatureverificationex-method.md)|Получает значение, указывающее, содержит ли находящийся по указанному пути манифест сборки подпись строгого имени.|  
|[Метод StrongNameSignatureVerificationFromImage](iclrstrongname-strongnamesignatureverificationfromimage-method.md)|Проверяет допустимость сборки, которая уже была сопоставлена с памятью, для связанного открытого ключа.|  
|[Метод StrongNameTokenFromAssembly](iclrstrongname-strongnametokenfromassembly-method.md)|Создает маркер строгого имени из указанного файла сборки.|  
|[Метод StrongNameTokenFromAssemblyEx](iclrstrongname-strongnametokenfromassemblyex-method.md)|Создает маркер строгого имени из указанного файла сборки и возвращает открытый ключ.|  
|[Метод StrongNameTokenFromPublicKey](iclrstrongname-strongnametokenfrompublickey-method.md)|Получает маркер, представляющий открытый ключ.|  
  
## <a name="remarks"></a>Комментарии  
 Экземпляр компонента можно получить `ICLRStrongName` , вызвав метод [ICLRRuntimeInfo::](iclrruntimeinfo-getinterface-method.md) WebMethod с использованием `CLSID_CLRStrongName` и `IID_ICLRStrongName` в качестве параметров.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Метахост. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](hosting-interfaces.md)
- [Размещение](index.md)

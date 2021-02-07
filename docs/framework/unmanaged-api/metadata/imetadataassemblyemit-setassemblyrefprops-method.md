---
description: 'Дополнительные сведения о методе: IMetaDataAssemblyEmit:: Сетассемблирефпропс'
title: Метод IMetaDataAssemblyEmit::SetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyRefProps
helpviewer_keywords:
- SetAssemblyRefProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 70a32bf3-9051-4f96-ae87-11356d06a073
topic_type:
- apiref
ms.openlocfilehash: 704fff656b705bb246e2742ce991d41fcadcdfcd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678176"
---
# <a name="imetadataassemblyemitsetassemblyrefprops-method"></a>Метод IMetaDataAssemblyEmit::SetAssemblyRefProps

Изменяет указанную структуру метаданных `AssemblyRef`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetAssemblyRefProps (  
    [in] mdAssemblyRef              ar,  
    [in] const void                 *pbPublicKeyOrToken,  
    [in] ULONG                      cbPublicKeyOrToken,  
    [in] LPCWSTR                    szName,
    [in] const ASSEMBLYMETADATA     *pMetaData,
    [in] const void                 *pbHashValue,  
    [in] ULONG                      cbHashValue,  
    [in] DWORD                      dwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ar`  
 окне Токен метаданных, указывающий `AssemblyRef` структуру метаданных, которую необходимо изменить.  
  
 `pbPublicKeyOrToken`  
 окне Открытый ключ издателя сборки, на которую указывает ссылка.  
  
 `cbPublicKeyOrToken`  
 окне Размер в байтах для `pbPublicKeyOrToken` .  
  
 `szName`  
 окне Понятное для человека текстовое имя сборки.  
  
 `pMetaData`  
 окне Указатель на экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформе и локали для сборки.  
  
 `pbHashValue`  
 окне Указатель на хэш-данные, связанные со сборкой.  
  
 `cbHashValue`  
 окне Размер в байтах для `pbHashValue` .  
  
 `dwAssemblyRefFlags`  
 окне Побитовое сочетание значений [ассемблиреффлагс](assemblyrefflags-enumeration.md) , задающих атрибуты упоминаемой сборки.  
  
## <a name="remarks"></a>Remarks  

 Чтобы создать `AssemblyRef` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинеассемблиреф](imetadataassemblyemit-defineassemblyref-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)

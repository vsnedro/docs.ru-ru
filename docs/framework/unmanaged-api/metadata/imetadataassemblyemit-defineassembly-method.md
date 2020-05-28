---
title: Метод IMetaDataAssemblyEmit::DefineAssembly
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 17c91200730431c4c6e230b8c1561ce7c4863868
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008187"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a>Метод IMetaDataAssemblyEmit::DefineAssembly
Создает `Assembly` структуру, содержащую метаданные для указанной сборки, и возвращает связанный маркер метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbPublicKey`  
 окне Открытый ключ, определяющий издателя сборки, или значение NULL, если сборка не имеет строгого имени.  
  
 `cbPublicKey`  
 окне Размер в байтах для `pbPublicKey` .  
  
 `uHashAlgId`  
 окне Идентификатор алгоритма хэширования, используемого для шифрования файлов в сборке, или значение NULL для указания алгоритма SHA-1.  
  
 `szName`  
 окне Понятное для человека текстовое имя сборки. Это значение не должно превышать 1024 символов.  
  
 `pMetaData`  
 окне Указатель на экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформе и локали для сборки.  
  
 `dwAssemblyFlags`  
 окне Сочетание значений [корассемблифлагс](corassemblyflags-enumeration.md) , описывающих функции сборки.  
  
 `pmda`  
 заполняет Указатель на маркер метаданных.  
  
## <a name="remarks"></a>Примечания  
 `Assembly`В манифесте может быть определена только одна структура метаданных.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)

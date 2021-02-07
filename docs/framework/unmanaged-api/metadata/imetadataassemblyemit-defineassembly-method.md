---
description: 'Дополнительные сведения о методе: IMetaDataAssemblyEmit::D Ефинеассембли'
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
ms.openlocfilehash: cd53a4398f49ca96072fc5f5b6dcac35a94bdc59
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706764"
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
  
## <a name="remarks"></a>Remarks  

 `Assembly`В манифесте может быть определена только одна структура метаданных.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)

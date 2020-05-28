---
title: Метод IMetaDataAssemblyEmit::DefineAssemblyRef
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssemblyRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssemblyRef
helpviewer_keywords:
- DefineAssemblyRef method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineAssemblyRef method [.NET Framework metadata]
ms.assetid: 0b284b18-0084-4b3a-912a-5ebe9f29c88b
topic_type:
- apiref
ms.openlocfilehash: 612463bca18c23fac0b086adde2d208a0fbc5ae5
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008174"
---
# <a name="imetadataassemblyemitdefineassemblyref-method"></a>Метод IMetaDataAssemblyEmit::DefineAssemblyRef
Создает структуру `AssemblyRef`, содержащую метаданные для сборки, на которую ссылается данная сборка, и возвращает связанный токен метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineAssemblyRef (  
    [in]  void                *pbPublicKeyOrToken,  
    [in]  ULONG               cbPublicKeyOrToken,  
    [in]  LPCWSTR             szName,  
    [in]  ASSEMBLYMETADATA    pMetaData,  
    [in]  void                *pbHashValue,  
    [in]  ULONG               cbHashValue,  
    [in]  DWORD               dwAssemblyRefFlags,  
    [out] mdAssemblyRef       *pmdar  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pbPublicKeyOrToken`  
 окне Открытый ключ издателя сборки, на которую указывает ссылка. Вспомогательную функцию [StrongNameTokenFromAssembly](../strong-naming/strongnametokenfromassembly-function.md) можно использовать, чтобы получить хэш открытого ключа для передачи в качестве этого параметра.  
  
 `cbPublicKeyOrToken`  
 окне Размер в байтах для `pbPublicKeyOrToken` .  
  
 `szName`  
 окне Понятное для человека текстовое имя сборки. Это значение не должно превышать 1024 символов.  
  
 `pMetaData`  
 окне Экземпляр ASSEMBLYMETADATA, содержащий сведения о версии, платформе и языковой стандарте сборки, на которую указывает ссылка.  
  
 `pbHashValue`  
 окне Хэш-данные, связанные с упоминаемой сборкой. Необязательный параметр.  
  
 `cbHashValue`  
 окне Размер в байтах для `pbHashValue` .  
  
 `dwAssemblyRefFlags`  
 окне Побитовое сочетание значений [корассемблифлагс](corassemblyflags-enumeration.md) , влияющих на поведение подсистемы выполнения.  
  
 `pmdar`  
 заполняет Указатель на возвращаемый `AssemblyRef` маркер метаданных.  
  
## <a name="remarks"></a>Примечания  
 `AssemblyRef`Для каждой сборки, на которую ссылается эта сборка, должна быть определена одна структура метаданных.  
  
 Во время выполнения сведения о сборке, на которую указывает ссылка, передаются распознавателю сборок с указанием, что они представляют "как встроенные" сведения. Затем сопоставитель сборок применяет политику.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также статью

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)

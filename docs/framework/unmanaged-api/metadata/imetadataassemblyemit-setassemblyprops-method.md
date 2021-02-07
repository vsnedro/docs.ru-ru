---
description: 'Дополнительные сведения о методе: IMetaDataAssemblyEmit:: Сетассемблипропс'
title: Метод IMetaDataAssemblyEmit::SetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
ms.openlocfilehash: d5dfb5fa472bb83863c8e4909998deeb2b9fc53b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678202"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a>Метод IMetaDataAssemblyEmit::SetAssemblyProps

Изменяет указанную структуру метаданных `Assembly`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pma`  
 окне Токен метаданных, указывающий `Assembly` структуру метаданных, которую необходимо изменить.  
  
 `pbPublicKey`  
 окне Указатель на открытый ключ издателя сборки.  
  
 `cbPublicKey`  
 окне Размер в байтах для `pbPublicKey` .  
  
 `ulHashAlgId`  
 окне Идентификатор хэш-алгоритма, используемого для хэширования файлов сборки.  
  
 `szName`  
 окне Понятное для человека текстовое имя сборки.  
  
 `pMetaData`  
 окне Указатель на ASSEMBLYMETADATA, содержащий сведения о версии, платформе и локали для сборки.  
  
 `dwAssemblyFlags`  
 окне Побитовое сочетание значений [AssemblyFlags](assemblyflags-enumeration.md) , задающих различные атрибуты сборки.  
  
## <a name="remarks"></a>Remarks  

 Чтобы создать `Assembly` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефинеассембли](imetadataassemblyemit-defineassembly-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)

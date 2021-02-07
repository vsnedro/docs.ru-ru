---
description: 'Дополнительные сведения о методе: IMetaDataAssemblyEmit:: Сетекспортедтипепропс'
title: Метод IMetaDataAssemblyEmit::SetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetExportedTypeProps
helpviewer_keywords:
- SetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 1c090153-fd5f-46c7-9cff-39a78d992c8f
topic_type:
- apiref
ms.openlocfilehash: 61032abd7b049af29c583e9aee126184af3c78f2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678111"
---
# <a name="imetadataassemblyemitsetexportedtypeprops-method"></a>Метод IMetaDataAssemblyEmit::SetExportedTypeProps

Изменяет указанную структуру метаданных `ExportedType`.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetExportedTypeProps (  
    [in] mdExportedType   ct,
    [in] mdToken          tkImplementation,  
    [in] mdTypeDef        tkTypeDef,  
    [in] DWORD            dwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `ct`  
 окне Токен метаданных, указывающий `ExportedType` структуру метаданных, которую необходимо изменить.  
  
 `tkImplementation`  
 окне Токен типа `File` , `AssemblyRef` или, `ExportedType` который указывает, как этот тип реализуется.  
  
 `tkTypeDef`  
 окне `TypeDef` Токен, на который ссылается файл кода.  
  
 `dwExportedTypeFlags`  
 окне Побитовое сочетание значений, определяющих атрибуты типа.  
  
## <a name="remarks"></a>Remarks  

 Чтобы создать `ExportedType` структуру метаданных, используйте метод [IMetaDataAssemblyEmit::D ефиникспортедтипе](imetadataassemblyemit-defineexportedtype-method.md) .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)

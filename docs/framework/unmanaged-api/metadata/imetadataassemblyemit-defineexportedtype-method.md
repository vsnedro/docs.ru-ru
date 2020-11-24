---
title: Метод IMetaDataAssemblyEmit::DefineExportedType
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
ms.openlocfilehash: 6b30218cc7373494870ec54a3196857fcc5c08a5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689427"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>Метод IMetaDataAssemblyEmit::DefineExportedType

Создает структуру `ExportedType`, содержащую метаданные для указанного экспортированного типа, и возвращает связанный токен метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `szName`  
 окне Имя экспортируемого типа. Для версии 1,1 среды CLR имя экспортируемого типа должно точно совпадать с именем, заданным в `TypeDef` для типа.  
  
 `tkImplementation`  
 окне Токен, указывающий, где реализуется экспортируемый тип. Допустимые значения и их связанное с ними значение:  
  
- `mdFile` Тип реализуется в другом файле в этой сборке.  
  
- `mdAssemblyRef` Тип реализован в другой сборке.  
  
- `mdExportedTYpe` Тип вложен в другой тип.  
  
- `mdFileNil` Тип находится в том же файле, что и манифест, и не является вложенным типом.  
  
 `tkTypeDef`  
 окне Токен метаданных, указывающий тип для экспорта. Это значение вводится в `TypeDef` таблицу в файле, который реализует тип, и имеет смысл только в том случае, если этот файл находится в этой сборке.  
  
 `dwExportedTypeFlags`  
 окне Побитовое сочетание значений перечисления [кортипеаттр](cortypeattr-enumeration.md) , определяющих настройки свойств для экспортируемого типа.  
  
 `pmdct`  
 заполняет Указатель на возвращаемый маркер метаданных, указывающий на экспортируемый тип.  
  
## <a name="remarks"></a>Комментарии  

 `ExportedType`Структура метаданных должна быть определена для каждого типа, предоставляемого этой сборкой и реализованного в модуле, отличном от того, который содержит манифест.  
  
## <a name="requirements"></a>Требования  

 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)

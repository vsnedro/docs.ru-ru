---
description: 'Дополнительные сведения: IMetaDataEmit::D метод Ефинетипедеф'
title: Метод IMetaDataEmit::DefineTypeDef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
ms.openlocfilehash: ca0c74b8c067771e9f45a8c00639d75c9ad08de1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784045"
---
# <a name="imetadataemitdefinetypedef-method"></a>Метод IMetaDataEmit::DefineTypeDef

Создает определение типа для типа среды CLR и получает маркер метаданных для этого определения типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineTypeDef (
    [in]  LPCWSTR     szTypeDef,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `szTypeDef`  
 окне Имя типа в Юникоде.  
  
 `dwTypeDefFlags`  
 [входные] `TypeDef` атрибута. Это битовая маска `CoreTypeAttr` значений.  
  
 `tkExtends`  
 окне Маркер базового класса. Он должен быть либо `mdTypeDef` `mdTypeRef` маркером, либо.  
  
 `rtkImplements`  
 окне Массив токенов, указывающий интерфейсы, реализуемые этим классом или интерфейсом.  
  
 `ptd`  
 заполняет `mdTypeDef` Назначенный маркер.  
  
## <a name="remarks"></a>Remarks  

 Флаг в `dwTypeDefFlags` указывает, является ли создаваемый тип ссылочным типом системы общих типов (класс или интерфейс) или типом значения системы общего типа.  
  
 В зависимости от предоставленных параметров этот метод, как побочный результат, может также создавать `mdInterfaceImpl` запись для каждого интерфейса, который наследуется или реализуется этим типом. Однако этот метод не возвращает ни одного из этих `mdInterfaceImpl` токенов. Если клиент хочет позже добавить или изменить `mdInterfaceImpl` маркер, он должен использовать `IMetaDataImport` интерфейс для перечисления. Если вы хотите использовать семантику интерфейса COM, необходимо `[default]` предоставить интерфейс по умолчанию в качестве первого элемента в `rtkImplements` ; настраиваемый атрибут, заданный для класса, указывает, что класс имеет интерфейс по умолчанию (который всегда считается первым `mdInterfaceImpl` маркером, объявленным для класса).  
  
 Каждый элемент `rtkImplements` массива содержит `mdTypeDef` `mdTypeRef` токен или. Последний элемент в массиве должен быть `mdTokenNil` .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)

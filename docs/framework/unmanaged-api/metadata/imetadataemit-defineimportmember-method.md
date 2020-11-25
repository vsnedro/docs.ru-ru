---
title: Метод IMetaDataEmit::DefineImportMember
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
ms.openlocfilehash: 60210bc8f93294c3c3380c36096f3e80e5b26643
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723263"
---
# <a name="imetadataemitdefineimportmember-method"></a>Метод IMetaDataEmit::DefineImportMember

Создает ссылку на указанный элемент типа или модуля, который определен за пределами текущей области, и определяет маркер для этой ссылки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT DefineImportMember (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,
    [in]  mdToken                  mbMember,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [in]  mdToken                  tkParent,
    [out] mdMemberRef              *pmr
);  
```  
  
## <a name="parameters"></a>Параметры  

 `pAssemImport`  
 окне Интерфейс [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) , представляющий сборку, из которой импортируется целевой элемент.  
  
 `pbHashValue`  
 окне Массив, содержащий хэш для сборки, заданной параметром `pAssemImport` .  
  
 `cbHashValue`  
 [in] Число байтов в массиве `pbHashValue`.  
  
 `pImport`  
 окне Интерфейс [IMetaDataImport](imetadataimport-interface.md) , представляющий область метаданных, из которой импортируется целевой элемент.  
  
 `mbMember`  
 окне Токен метаданных, указывающий целевой элемент. Токен может быть `mdMethodDef` (для метода-члена), `mdProperty` (для свойства элемента) или `mdFieldDef` токена (для поля члена).  
  
 `pAssemEmit`  
 окне Интерфейс [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) , представляющий сборку, в которую импортируется целевой элемент.  
  
 `tkParent`  
 окне `mdTypeRef` Токен или `mdModuleRef` для типа или модуля соответственно, которому принадлежит целевой элемент.  
  
 `pmr`  
 заполняет `mdMemberRef` Токен, определенный в текущей области для ссылки на элемент.  
  
## <a name="remarks"></a>Комментарии  

 `DefineImportMember`Метод ищет элемент, заданный параметром `mbMember` , который определен в другой области, заданной параметром `pImport` , и извлекает его свойства. Эта информация используется для вызова метода [IMetaDataEmit::D ефинемемберреф](imetadataemit-definememberref-method.md) в текущей области для создания ссылки на элемент.  
  
 Как правило, перед использованием `DefineImportMember` метода необходимо создать в текущей области ссылку на тип или ссылку на модуль для родительского класса, интерфейса или модуля целевого элемента. Затем маркер метаданных для этой ссылки передается в `tkParent` аргумент. Не нужно создавать ссылку на родительский элемент целевого элемента, если он будет разрешен позже компилятором или компоновщиком. Подведение итогов.  
  
- Если целевой элемент является полем или методом, используйте метод [IMetaDataEmit::D ефинетиперефбинаме](imetadataemit-definetyperefbyname-method.md) или [IMetaDataEmit::D ефинеимпорттипе](imetadataemit-defineimporttype-method.md) для создания ссылки на тип в текущей области для родительского класса члена или родительского интерфейса.  
  
- Если целевой элемент является глобальной переменной или глобальной функцией (то есть не членом класса или интерфейса), используйте метод [IMetaDataEmit::D ефинемодулереф](imetadataemit-definemoduleref-method.md) , чтобы создать ссылку на модуль в текущей области для родительского модуля элемента.  
  
- Значение, если родительский элемент целевого элемента будет разрешен позже компилятором или компоновщиком, а затем `mdTokenNil` передан `tkParent` . Единственный сценарий, в котором это применимо, — это то, что глобальная функция или глобальная переменная импортируется из OBJ-файла, который в конечном итоге будет связан с текущим модулем и объединенными метаданными.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)

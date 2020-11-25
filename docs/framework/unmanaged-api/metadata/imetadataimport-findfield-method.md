---
title: Метод IMetaDataImport::FindField
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindField
helpviewer_keywords:
- IMetaDataImport::FindField method [.NET Framework metadata]
- FindField method [.NET Framework metadata]
ms.assetid: 38cd4e16-fbb2-471c-aa73-ac51a1931ad2
topic_type:
- apiref
ms.openlocfilehash: 9b42f0f7c8e2878ee3ec140344f51517a24247c4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729867"
---
# <a name="imetadataimportfindfield-method"></a>Метод IMetaDataImport::FindField

Возвращает указатель на токен FieldDef для поля, заключенного в заданный объект с <xref:System.Type> указанным именем и сигнатурой метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FindField (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,  
   [in]  PCCOR_SIGNATURE   pvSigBlob,  
   [in]  ULONG             cbSigBlob,  
   [out] mdFieldDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `td`  
 окне Маркер TypeDef для класса или интерфейса, который заключает поле для поиска. Если это значение равно `mdTokenNil` , поиск выполняется для глобальной переменной.  
  
 `szName`  
 окне Имя искомого поля.  
  
 `pvSigBlob`  
 окне Указатель на сигнатуру двоичных метаданных поля.  
  
 `cbSigBlob`  
 окне Размер в байтах для `pvSigBlob` .  
  
 `pmb`  
 заполняет Указатель на соответствующий токен FieldDef.  
  
## <a name="remarks"></a>Комментарии  

 Поле указывается с помощью включающего его класса или интерфейса ( `td` ), имени ( `szName` ) и (при необходимости) его сигнатуры ( `pvSigBlob` ).  
  
 Подпись, передаваемая в `FindField` , должна быть создана в текущей области, так как сигнатуры привязаны к определенной области. Сигнатура может внедрять маркер, идентифицирующий включающий класс или тип значения. (Токен является индексом локальной таблицы TypeDef). Нельзя построить подпись времени выполнения вне контекста текущей области и использовать эту сигнатуру в качестве входных данных для `FindField` .  
  
 `FindField` находит только поля, которые были определены непосредственно в классе или интерфейсе; наследуемые поля не находятся.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

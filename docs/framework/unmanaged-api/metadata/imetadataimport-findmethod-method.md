---
title: Метод IMetaDataImport::FindMethod
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMethod
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMethod
helpviewer_keywords:
- FindMethod method [.NET Framework metadata]
- IMetaDataImport::FindMethod method [.NET Framework metadata]
ms.assetid: 0f9bde1d-e306-438d-941b-d0925b322304
topic_type:
- apiref
ms.openlocfilehash: c2ec907759a25048444ebcc81bf5bb0fd23ced58
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503657"
---
# <a name="imetadataimportfindmethod-method"></a>Метод IMetaDataImport::FindMethod
Возвращает указатель на токен MethodDef для метода, заключенного в заданный объект с <xref:System.Type> указанным именем и сигнатурой метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FindMethod (  
   [in]  mdTypeDef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMethodDef        *pmb  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `td`  
 окне `mdTypeDef`Токен для типа (класса или интерфейса), который включает член для поиска. Если это значение равно `mdTokenNil` , то поиск выполняется для глобальной функции.  
  
 `szName`  
 окне Имя искомого метода.  
  
 `pvSigBlob`  
 окне Указатель на сигнатуру двоичных метаданных метода.  
  
 `cbSigBlob`  
 окне Размер в байтах для `pvSigBlob` .  
  
 `pmb`  
 заполняет Указатель на соответствующий токен MethodDef.  
  
## <a name="remarks"></a>Примечания  
 Метод указывается с помощью включающего класса или интерфейса ( `td` ), его имени ( `szName` ) и (при необходимости) его сигнатуры ( `pvSigBlob` ). В классе или интерфейсе может быть несколько методов с одинаковым именем. В этом случае передайте сигнатуру метода, чтобы найти уникальное совпадение.  
  
 Подпись, передаваемая в `FindMethod` , должна быть создана в текущей области, так как сигнатуры привязаны к определенной области. Сигнатура может внедрять маркер, идентифицирующий включающий класс или тип значения. Токен является индексом локальной таблицы TypeDef. Нельзя построить сигнатуру времени выполнения вне контекста текущей области и использовать эту сигнатуру в качестве входных данных для входных данных `FindMethod` .  
  
 `FindMethod`находит только методы, которые были определены непосредственно в классе или интерфейсе; Он не находит унаследованные методы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Reflection.MethodInfo>
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

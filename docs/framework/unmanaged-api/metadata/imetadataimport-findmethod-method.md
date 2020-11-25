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
ms.openlocfilehash: 111e42a6d8f413c616779bc44e0722ab38781588
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711342"
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
 окне `mdTypeDef` Токен для типа (класса или интерфейса), который включает член для поиска. Если это значение равно `mdTokenNil` , то поиск выполняется для глобальной функции.  
  
 `szName`  
 окне Имя искомого метода.  
  
 `pvSigBlob`  
 окне Указатель на сигнатуру двоичных метаданных метода.  
  
 `cbSigBlob`  
 окне Размер в байтах для `pvSigBlob` .  
  
 `pmb`  
 заполняет Указатель на соответствующий токен MethodDef.  
  
## <a name="remarks"></a>Комментарии  

 Метод указывается с помощью включающего класса или интерфейса ( `td` ), его имени ( `szName` ) и (при необходимости) его сигнатуры ( `pvSigBlob` ). В классе или интерфейсе может быть несколько методов с одинаковым именем. В этом случае передайте сигнатуру метода, чтобы найти уникальное совпадение.  
  
 Подпись, передаваемая в `FindMethod` , должна быть создана в текущей области, так как сигнатуры привязаны к определенной области. Сигнатура может внедрять маркер, идентифицирующий включающий класс или тип значения. Токен является индексом локальной таблицы TypeDef. Нельзя построить сигнатуру времени выполнения вне контекста текущей области и использовать эту сигнатуру в качестве входных данных для входных данных `FindMethod` .  
  
 `FindMethod` находит только методы, которые были определены непосредственно в классе или интерфейсе; Он не находит унаследованные методы.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Reflection.MethodInfo>
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

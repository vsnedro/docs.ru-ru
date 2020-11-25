---
title: Метод IMetaDataImport::FindMemberRef
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMemberRef
helpviewer_keywords:
- IMetaDataImport::FindMemberRef method [.NET Framework metadata]
- FindMemberRef method [.NET Framework metadata]
ms.assetid: 1ccda329-d752-4d89-abe8-511af3c3f4c9
topic_type:
- apiref
ms.openlocfilehash: 0ba25c981cc389baf06ecca0db543d48ac60317b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711407"
---
# <a name="imetadataimportfindmemberref-method"></a>Метод IMetaDataImport::FindMemberRef

Возвращает указатель на токен MemberRef для ссылки на элемент, заключенный в заданный объект с <xref:System.Type> указанным именем и сигнатурой метаданных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT FindMemberRef (  
   [in]  mdTypeRef          td,  
   [in]  LPCWSTR            szName,
   [in]  PCCOR_SIGNATURE    pvSigBlob,
   [in]  ULONG              cbSigBlob,
   [out] mdMemberRef        *pmr  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `td`  
 окне Токен TypeRef для класса или интерфейса, который заключает в себя ссылку на элемент для поиска. Если это значение равно `mdTokenNil` , поиск выполняется для глобальной переменной или ссылки на глобальную функцию.  
  
 `szName`  
 окне Имя искомой ссылки на член.  
  
 `pvSigBlob`  
 окне Указатель на сигнатуру двоичных метаданных ссылки на элемент.  
  
 `cbSigBlob`  
 окне Размер в байтах для `pvSigBlob` .  
  
 `pmr`  
 заполняет Указатель на соответствующий токен MemberRef.  
  
## <a name="remarks"></a>Комментарии  

 Элемент указывается с помощью включающего класса или интерфейса ( `td` ), его имени ( `szName` ) и (при необходимости) его сигнатуры ( `pvSigBlob` ).  
  
 Подпись, передаваемая в `FindMemberRef` , должна быть создана в текущей области, так как сигнатуры привязаны к определенной области. Сигнатура может внедрять маркер, идентифицирующий включающий класс или тип значения. Токен является индексом локальной таблицы TypeDef. Нельзя построить подпись времени выполнения вне контекста текущей области и использовать эту сигнатуру в качестве входных данных для `FindMemberRef` .  
  
 `FindMemberRef` находит только ссылки на элементы, которые были определены непосредственно в классе или интерфейсе; Он не находит унаследованные ссылки на члены.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

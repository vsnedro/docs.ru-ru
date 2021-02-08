---
description: 'Дополнительные сведения о: интерфейс IMetaDataTables'
title: Интерфейс IMetaDataTables
ms.date: 03/30/2017
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
ms.openlocfilehash: c3edf504586bad1252c36d6e8254193eaf9cc26d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799276"
---
# <a name="imetadatatables-interface"></a>Интерфейс IMetaDataTables

Предоставляет методы для хранения и извлечения сведений о метаданных в таблицах.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetBlob](imetadatatables-getblob-method.md)|Возвращает указатель на большой двоичный объект (BLOB) по указанному индексу столбца.|  
|[Метод GetBlobHeapSize](imetadatatables-getblobheapsize-method.md)|Возвращает размер кучи больших двоичных объектов в байтах.|  
|[Метод GetCodedTokenInfo](imetadatatables-getcodedtokeninfo-method.md)|Возвращает указатель на массив токенов, связанных с указанным индексом строки.|  
|[Метод GetColumn](imetadatatables-getcolumn-method.md)|Возвращает указатель на значения, содержащиеся в столбце по указанному индексу столбца в таблице по указанному индексу таблицы.|  
|[Метод GetColumnInfo](imetadatatables-getcolumninfo-method.md)|Получает данные о указанном столбце в указанной таблице.|  
|[Метод GetGuid](imetadatatables-getguid-method.md)|Возвращает идентификатор GUID из строки по указанному индексу.|  
|[Метод GetGuidHeapSize](imetadatatables-getguidheapsize-method.md)|Возвращает размер кучи GUID в байтах.|  
|[Метод GetNextBlob](imetadatatables-getnextblob-method.md)|Возвращает индекс следующего большого двоичного объекта в таблице.|  
|[Метод GetNextGuid](imetadatatables-getnextguid-method.md)|Возвращает индекс следующего значения GUID в текущем столбце таблицы.|  
|[Метод GetNextString](imetadatatables-getnextstring-method.md)|Возвращает индекс следующей строки в текущем столбце таблицы.|  
|[Метод GetNextUserString](imetadatatables-getnextuserstring-method.md)|Возвращает индекс строки, содержащей следующую жестко заданную строку в текущем столбце таблицы.|  
|[Метод GetNumTables](imetadatatables-getnumtables-method.md)|Возвращает количество таблиц в области текущего `IMetaDataTables` экземпляра.|  
|[Метод GetRow](imetadatatables-getrow-method.md)|Возвращает строку по указанному индексу строки в таблице по указанному индексу таблицы.|  
|[Метод GetString](imetadatatables-getstring-method.md)|Возвращает строку по указанному индексу из столбца таблицы в области текущей ссылки.|  
|[Метод GetStringHeapSize](imetadatatables-getstringheapsize-method.md)|Возвращает размер кучи строк (в байтах).|  
|[Метод GetTableIndex](imetadatatables-gettableindex-method.md)|Возвращает индекс для таблицы, на которую ссылается указанный токен.|  
|[Метод GetTableInfo](imetadatatables-gettableinfo-method.md)|Возвращает имя, размер строки, число строк, число столбцов и индекс ключевого столбца таблицы по указанному индексу таблицы.|  
|[Метод GetUserString](imetadatatables-getuserstring-method.md)|Получает жестко заданную строку по указанному индексу в строковом столбце текущей области.|  
|[Метод GetUserStringHeapSize](imetadatatables-getuserstringheapsize-method.md)|Возвращает размер (в байтах) кучи пользовательской строки.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](metadata-interfaces.md)
- [Интерфейс IMetaDataTables2](imetadatatables2-interface.md)

---
title: Метод IMetaDataTables::GetColumn
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: 270546f0270521e38cfdcae5e4d2137202c13cb1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711095"
---
# <a name="imetadatatablesgetcolumn-method"></a>Метод IMetaDataTables::GetColumn

Возвращает указатель на значение, содержащееся в ячейке указанного столбца и строки в заданной таблице.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a>Параметры

 `ixTbl`  
 окне Индекс таблицы.  
  
 `ixCol`  
 окне Индекс столбца в таблице.  
  
 `rid`  
 окне Индекс строки в таблице.  
  
 `pVal`  
 заполняет Указатель на значение в ячейке.  

## <a name="remarks"></a>Комментарии

Интерпретация значения, возвращаемого с помощью, `pVal` зависит от типа столбца. Тип столбца можно определить с помощью метода [IMetaDataTables. GetColumnInfo](imetadatatables-getcolumninfo-method.md).

- Метод **DataColumn** автоматически преобразует столбцы типа **RID** или **кодедтокен** в полные 32-разрядные `mdToken` значения.
- Он также автоматически преобразует 8-битные или 16-битные значения в полные 32-разрядные значения.
- Для столбцов типа *кучи* возвращенный *Pval* будет индексом в соответствующей куче.

| Тип столбца              | pVal содержит | Комментировать                          |
|--------------------------|---------------|-----------------------------------|
| `0`..`iRidMax`<br>(0.. 63)  | mdToken     | *Pval* будет содержать полный маркер. Функция автоматически преобразует RID в полный маркер. |
| `iCodedToken`..`iCodedTokenMax`<br>(64.. 95) | mdToken | После возврата *Pval* будет содержать полный маркер. Функция автоматически распаковывает Кодедтокен в полную лексему. |
| `iSHORT` (96)            | Int16         | Автоматический вход в 32-разрядный.  |
| `iUSHORT` (97)           | UInt16        | Автоматический вход в 32-разрядный.  |
| `iLONG` (98)             | Int32         |                                        |
| `iULONG` (99)            | UInt32        |                                        |
| `iBYTE` (100)            | Byte          | Автоматический вход в 32-разрядный.  |
| `iSTRING` (101)          | Индекс строковой кучи | *Pval* — это индекс в куче строк. Используйте [IMetadataTables:: GetString](imetadatatables-getstring-method.md) , чтобы получить фактическое строковое значение столбца. |
| `iGUID` (102)            | Индекс кучи GUID | *Pval* — это индекс в куче GUID. Чтобы получить действительное значение GUID столбца, используйте [IMetadataTables::](imetadatatables-getguid-method.md) DataColumn. |
| `iBLOB` (103)            | Индекс кучи больших двоичных объектов | *Pval* — это индекс в куче больших двоичных объектов. Для получения действительного значения большого двоичного объекта столбца используйте [IMetadataTables::-BLOB](imetadatatables-getblob-method.md) . |
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Версии .NET Framework**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс IMetaDataTables](imetadatatables-interface.md)
- [Интерфейс IMetaDataTables2](imetadatatables2-interface.md)

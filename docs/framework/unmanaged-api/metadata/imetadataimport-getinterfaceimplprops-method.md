---
title: Метод IMetaDataImport::GetInterfaceImplProps
ms.date: 02/25/2019
api_name:
- IMetaDataImport.GetInterfaceImplProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetInterfaceImplProps
helpviewer_keywords:
- IMetaDataImport::GetInterfaceImplProps method [.NET Framework metadata]
- GetInterfaceImpProps method [.NET Framework metadata]
ms.assetid: be3f5985-b1e4-4036-8602-c16e8508d4af
topic_type:
- apiref
ms.openlocfilehash: 1c9d9647084aa729817eeeb17ee3f5cd320c0d29
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491253"
---
# <a name="imetadataimportgetinterfaceimplprops-method"></a>Метод IMetaDataImport::GetInterfaceImplProps
Возвращает указатель на маркеры метаданных для <xref:System.Type> , который реализует указанный метод, и для интерфейса, объявляющего этот метод.
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetInterfaceImplProps (  
   [in]  mdInterfaceImpl        iiImpl,  
   [out] mdTypeDef              *pClass,  
   [out] mdToken                *ptkIface  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `iiImpl`  
 окне Токен метаданных, представляющий метод, для которого необходимо вернуть маркеры класса и интерфейса.  
  
 `pClass`  
 заполняет Маркер метаданных, представляющий класс, реализующий метод.  
  
 `ptkIface`  
 заполняет Токен метаданных, представляющий интерфейс, определяющий реализованный метод.  

## <a name="remarks"></a>Примечания

 Получить значение для можно `iImpl` путем вызова метода [енуминтерфацеимплс](imetadataimport-enuminterfaceimpls-method.md) .

 Например, предположим, что класс имеет `mdTypeDef` значение маркера 0x02000007 и реализует три интерфейса, типы которых имеют токены:

- 0x02000003 (TypeDef)
- 0x0100000A (TypeRef)
- 0x0200001C (TypeDef)

По сути, эта информация хранится в таблице реализации интерфейса следующим образом:

| Номер строки | Токен класса | Токен интерфейса |
|------------|-------------|-----------------|
| 4          |             |                 |
| 5          | 02000007    | 02000003        |
| 6          | 02000007    | 0100000A        |
| 7          |             |                 |
| 8          | 02000007    | 0200001C        |

Помните, что маркер является 4-байтовым значением:

- 3 младших байта содержат номер строки или RID.
- Верхний байт содержит тип токена — 0x09 для `mdtInterfaceImpl` .

`GetInterfaceImplProps`Возвращает информацию, удерживаемую в строке, токен которой вы задаете в `iImpl` аргументе.
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

---
description: 'Дополнительные сведения: метод IMetaDataImport:: EnumMethodSemantics'
title: Метод IMetaDataImport::EnumMethodSemantics
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
ms.openlocfilehash: 9819afb2d7974e9f705c6ff665d3414eade0ab90
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728286"
---
# <a name="imetadataimportenummethodsemantics-method"></a>Метод IMetaDataImport::EnumMethodSemantics

Перечисляет свойства и события их изменения, с которыми связан указанный метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `phEnum`  
 [вход, выход] Указатель на перечислитель. При первом вызове этого метода это значение должно быть равно NULL.  
  
 `mb`  
 окне Токен MethodDef, ограничивающий область перечисления.  
  
 `rEventProp`  
 заполняет Массив, используемый для хранения событий или свойств.  
  
 `cMax`  
 [in] Максимальный размер массива `rEventProp`.  
  
 `pcEventProp`  
 заполняет Количество событий или свойств, возвращаемых в `rEventProp` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumMethodSemantics` успешно возвращено.|  
|`S_FALSE`|Нет событий или свойств для перечисления. В этом случае значение `pcEventProp` равно нулю.|  
  
## <a name="remarks"></a>Remarks  

 Многие типы среды CLR определяют события *свойств* `Changed` и методы `On` *свойств* , `Changed` связанные с их свойствами. Например, <xref:System.Windows.Forms.Control?displayProperty=nameWithType> тип определяет <xref:System.Windows.Forms.Control.Font%2A> свойство, <xref:System.Windows.Forms.Control.FontChanged> событие и <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод. Метод доступа set <xref:System.Windows.Forms.Control.Font%2A> свойства вызывает <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод, который, в свою очередь, вызывает <xref:System.Windows.Forms.Control.FontChanged> событие. `EnumMethodSemantics` <xref:System.Windows.Forms.Control.OnFontChanged%2A> Чтобы получить ссылки на <xref:System.Windows.Forms.Control.Font%2A> свойство и событие, необходимо вызвать метод с помощью MethodDef для <xref:System.Windows.Forms.Control.FontChanged> .  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

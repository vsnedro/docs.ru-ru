---
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
ms.openlocfilehash: 213cbd955e3d47a49abde579a54af48641e225ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491931"
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
|`S_OK`|`EnumMethodSemantics`успешно возвращено.|  
|`S_FALSE`|Нет событий или свойств для перечисления. В этом случае значение `pcEventProp` равно нулю.|  
  
## <a name="remarks"></a>Примечания  
 Многие типы среды CLR определяют события *свойств* `Changed` и методы `On` *свойств* , `Changed` связанные с их свойствами. Например, <xref:System.Windows.Forms.Control?displayProperty=nameWithType> тип определяет <xref:System.Windows.Forms.Control.Font%2A> свойство, <xref:System.Windows.Forms.Control.FontChanged> событие и <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод. Метод доступа set <xref:System.Windows.Forms.Control.Font%2A> свойства вызывает <xref:System.Windows.Forms.Control.OnFontChanged%2A> метод, который, в свою очередь, вызывает <xref:System.Windows.Forms.Control.FontChanged> событие. `EnumMethodSemantics` <xref:System.Windows.Forms.Control.OnFontChanged%2A> Чтобы получить ссылки на <xref:System.Windows.Forms.Control.Font%2A> свойство и событие, необходимо вызвать метод с помощью MethodDef для <xref:System.Windows.Forms.Control.FontChanged> .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

---
title: Метод IMetaDataImport::EnumMembers
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
ms.openlocfilehash: cc3bc5140da0634b5172f6253de3de37bff487f1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492063"
---
# <a name="imetadataimportenummembers-method"></a>Метод IMetaDataImport::EnumMembers
Перечисляет токены MemberDef, представляющие члены указанного типа.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `phEnum`  
 [вход, выход] Указатель на перечислитель.  
  
 `cl`  
 окне Токен TypeDef, представляющий тип, элементы которого необходимо перечислить.  
  
 `rMembers`  
 заполняет Массив, используемый для хранения маркеров Мембердеф.  
  
 `cMax`  
 [in] Максимальный размер массива `rMembers`.  
  
 `pcTokens`  
 заполняет Фактическое число токенов Мембердеф, возвращаемых в `rMembers` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|`S_OK`|`EnumMembers`успешно возвращено.|  
|`S_FALSE`|Нет токенов Мембердеф для перечисления. В этом случае значение `pcTokens` равно нулю.|  
  
## <a name="remarks"></a>Примечания  
 При перечислении коллекций элементов для класса `EnumMembers` возвращает только элементы (поля и методы, но **не** свойства или события), определенные непосредственно в классе. Он не возвращает члены, наследуемые классом, даже если класс предоставляет реализацию для этих унаследованных членов. Чтобы перечислить унаследованные члены, вызывающий объект должен явно пройти по цепочке наследования. Обратите внимание, что правила для цепочки наследования могут различаться в зависимости от языка или компилятора, который выдал исходные метаданные.

 Свойства и события не перечисляются с помощью `EnumMembers` . Чтобы перечислить их, используйте [енумпропертиес](imetadataimport-enumproperties-method.md) или [EnumEvents](imetadataimport-enumevents-method.md).
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MsCorEE. dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

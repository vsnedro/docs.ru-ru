---
description: 'Дополнительные сведения: метод IMetaDataImport:: EnumMembers'
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
ms.openlocfilehash: 3b56b25c6c581f6bfc3303a55a49a12ffcc73494
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670818"
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
|`S_OK`|`EnumMembers` успешно возвращено.|  
|`S_FALSE`|Нет токенов Мембердеф для перечисления. В этом случае значение `pcTokens` равно нулю.|  
  
## <a name="remarks"></a>Remarks  

 При перечислении коллекций элементов для класса `EnumMembers` возвращает только элементы (поля и методы, но **не** свойства или события), определенные непосредственно в классе. Он не возвращает члены, наследуемые классом, даже если класс предоставляет реализацию для этих унаследованных членов. Чтобы перечислить унаследованные члены, вызывающий объект должен явно пройти по цепочке наследования. Обратите внимание, что правила для цепочки наследования могут различаться в зависимости от языка или компилятора, который выдал исходные метаданные.

 Свойства и события не перечисляются с помощью `EnumMembers` . Чтобы перечислить их, используйте [енумпропертиес](imetadataimport-enumproperties-method.md) или [EnumEvents](imetadataimport-enumevents-method.md).
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Включается в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataImport](imetadataimport-interface.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

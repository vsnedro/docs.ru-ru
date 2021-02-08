---
description: 'Дополнительные сведения: Метод IMetaDataEmit:: GetSaveSize'
title: Метод IMetaDataEmit::GetSaveSize
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetSaveSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetSaveSize
helpviewer_keywords:
- IMetaDataEmit::GetSaveSize method [.NET Framework metadata]
- GetSaveSize method [.NET Framework metadata]
ms.assetid: 8aea2e2c-23a3-4cda-9a06-e19f97383830
topic_type:
- apiref
ms.openlocfilehash: 871e9f911eaaf1b1a7259466402e492d75aa7fb8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783941"
---
# <a name="imetadataemitgetsavesize-method"></a>Метод IMetaDataEmit::GetSaveSize

Возвращает приблизительный двоичный размер сборки и ее метаданных в текущей области.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetSaveSize (  
    [in]  CorSaveSize fSave,  
    [out] DWORD       *pdwSaveSize  
);  
```  
  
## <a name="parameters"></a>Параметры  

 `fSave`  
 окне Значение перечисления [корсавесизе](corsavesize-enumeration.md) , указывающее, следует ли получить точный или приблизительный размер. Допустимы только три значения: Кссаккурате, Ксскуикк и Кссдискардтрансиенткас:  
  
- Кссаккурате возвращает точный размер сохранения, но для его вычисления требуется больше времени.  
  
- Ксскуикк возвращает размер, дополненный для безопасности, но требует меньше времени для вычисления.  
  
- Кссдискардтрансиенткас сообщает `GetSaveSize` , что он может создавать неразрешенные настраиваемые атрибуты.  
  
 `pdwSaveSize`  
 заполняет Указатель на размер, необходимый для сохранения файла.  
  
## <a name="remarks"></a>Remarks  

 `GetSaveSize` Вычисляет пространство, необходимое в байтах, для сохранения сборки и всех ее метаданных в текущей области. (Вызов метода [IMetaDataEmit:: саветостреам](imetadataemit-savetostream-method.md) приведет к порождению этого числа байтов.)  
  
 Если вызывающий объект реализует интерфейс [IMapToken](imaptoken-interface.md) (через [IMetaDataEmit:: сесандлер](imetadataemit-sethandler-method.md) или [IMetaDataEmit:: Merge](imetadataemit-merge-method.md)), `GetSaveSize` выполняет два прохода по метаданным для оптимизации и сжатия. В противном случае оптимизация не выполняется.  
  
 Если выполняется оптимизация, первый проход просто сортирует структуры метаданных для настройки производительности поисков во время поиска. Этот шаг обычно приводит к перемещению записей, с побочным действием, что токены, сохраняемые средством для будущего использования, становятся недействительными. Однако метаданные не сообщают вызывающему объекту об изменениях токена до второго прохода. Во втором прохождении выполняются различные оптимизации, предназначенные для уменьшения общего размера метаданных, например для оптимизации (раннего связывания) `mdTypeRef` и `mdMemberRef` токенов, когда ссылка указывает на тип или член, объявленный в текущей области метаданных. На этом этапе выполняется еще один цикл сопоставления маркеров. После этого обработчик метаданных уведомляет вызывающий объект через свой `IMapToken` интерфейс о любых измененных значениях токенов.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MSCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IMetaDataEmit](imetadataemit-interface.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)

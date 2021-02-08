---
description: 'Дополнительные сведения о: интерфейс IMetaDataConverter'
title: Интерфейс IMetaDataConverter
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: 6ed84083bad924e760c576afe485bd7ccad012cf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789259"
---
# <a name="imetadataconverter-interface"></a>Интерфейс IMetaDataConverter

Предоставляет методы для сопоставления библиотек типов с их сигнатурами метаданных и для преобразования из одних в другие.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetMetaDataFromTypeInfo](imetadataconverter-getmetadatafromtypeinfo-method.md)|Возвращает указатель на экземпляр [IMetaDataImport](imetadataimport-interface.md) , представляющий сигнатуру метаданных для библиотеки типов, на которую ссылается указанный `ITypeInfo` экземпляр.|  
|[Метод GetMetaDataFromTypeLib](imetadataconverter-getmetadatafromtypelib-method.md)|Возвращает указатель на `IMetaDataImport` экземпляр, представляющий сигнатуру метаданных для библиотеки типов, представленной указанным `ITypeLib` экземпляром.|  
|[Метод GetTypeLibFromMetaData](imetadataconverter-gettypelibfrommetadata-method.md)|Возвращает указатель на `ITypeLib` экземпляр, представляющий библиотеку типов с указанными именами модуля и библиотеки.|  
  
## <a name="requirements"></a>Требования  

 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](metadata-interfaces.md)
- [Интерфейс IMetaDataImport](imetadataimport-interface.md)

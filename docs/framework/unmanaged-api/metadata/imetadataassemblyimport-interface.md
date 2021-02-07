---
description: 'Дополнительные сведения о: интерфейс IMetaDataAssemblyImport'
title: Интерфейс IMetaDataAssemblyImport
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: bb9c5163e4f5b68700e5a3836fa55edbbebac01c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753644"
---
# <a name="imetadataassemblyimport-interface"></a>Интерфейс IMetaDataAssemblyImport

Предоставляет методы для доступа и изучения содержимого манифеста сборки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CloseEnum](imetadataassemblyimport-closeenum-method.md)|Освобождает дескриптор указанного перечислителя.|  
|[Метод EnumAssemblyRefs](imetadataassemblyimport-enumassemblyrefs-method.md)|Возвращает указатель интерфейса на перечислитель, содержащий `mdAssemblyRef` маркеры сборок, на которые ссылается сборка в текущей области метаданных.|  
|[Метод EnumExportedTypes](imetadataassemblyimport-enumexportedtypes-method.md)|Возвращает указатель интерфейса на перечислитель, содержащий `mdExportedType` маркеры COM-типов, на которые ссылается сборка в текущей области метаданных.|  
|[Метод EnumFiles](imetadataassemblyimport-enumfiles-method.md)|Возвращает указатель интерфейса на перечислитель, содержащий `mdFile` маркеры файлов, на которые ссылается сборка в текущей области метаданных.|  
|[Метод EnumManifestResources](imetadataassemblyimport-enummanifestresources-method.md)|Возвращает указатель интерфейса на перечислитель, содержащий `mdManifestResource` маркеры ресурсов, на которые ссылается сборка в текущей области метаданных.|  
|[Метод FindAssembliesByName](imetadataassemblyimport-findassembliesbyname-method.md)|Возвращает массив `mdAssemblyRef` токенов для сборок с указанным именем.|  
|[Метод FindExportedTypeByName](imetadataassemblyimport-findexportedtypebyname-method.md)|Возвращает `mdExportedType` токен для типа COM с указанным именем.|  
|[Метод FindManifestResourceByName](imetadataassemblyimport-findmanifestresourcebyname-method.md)|Возвращает `mdManifestResource` токен для ресурса с указанным именем.|  
|[Метод GetAssemblyFromScop](imetadataassemblyimport-getassemblyfromscope-method.md)|Возвращает токен для сборки в текущей области метаданных.|  
|[Метод GetAssemblyProps](imetadataassemblyimport-getassemblyprops-method.md)|Возвращает параметры свойства указанной сборки.|  
|[Метод GetAssemblyRefProps](imetadataassemblyimport-getassemblyrefprops-method.md)|Возвращает параметры свойства указанного `mdAssemblyRef` токена.|  
|[Метод GetExportedTypeProps](imetadataassemblyimport-getexportedtypeprops-method.md)|Возвращает параметры свойства указанного типа COM.|  
|[Метод GetFileProps](imetadataassemblyimport-getfileprops-method.md)|Возвращает настройки свойств указанного файла.|  
|[Метод GetManifestResourceProps](imetadataassemblyimport-getmanifestresourceprops-method.md)|Возвращает параметры свойства указанного ресурса манифеста.|  
  
## <a name="requirements"></a>Требования  

 **Платформа:** См. раздел [требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](metadata-interfaces.md)
- [Интерфейс IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)

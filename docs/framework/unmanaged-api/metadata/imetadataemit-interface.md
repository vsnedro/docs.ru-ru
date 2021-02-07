---
description: Дополнительные сведения см. в статье об интерфейсе IMetaDataEmit.
title: Интерфейс IMetaDataEmit
ms.date: 03/30/2017
api_name:
- IMetaDataEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit
helpviewer_keywords:
- IMetaDataEmit interface [.NET Framework metadata]
ms.assetid: 3b48fd47-7397-4e2c-8bec-8157aa08978c
topic_type:
- apiref
ms.openlocfilehash: da8786f25e4081d3cc9c32cbb7ea7386d2e9f1f4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745987"
---
# <a name="imetadataemit-interface"></a>Интерфейс IMetaDataEmit

Предоставляет методы для создания, изменения и сохранения метаданных сборки в области, определенной в данный момент. Метаданные могут храниться в памяти или сохраняться на диск.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод ApplyEditAndContinue](imetadataemit-applyeditandcontinue-method.md)|Обновляет текущую область сборки с учетом изменений, внесенных в указанный объект `pImport` .|  
|[Метод DefineCustomAttribute](imetadataemit-definecustomattribute-method.md)|Создает определение для настраиваемого атрибута с указанной подписью метаданных, присоединяемого к указанному объекту и получает маркер для этого определения настраиваемого атрибута.|  
|[Метод DefineEvent](imetadataemit-defineevent-method.md)|Создает определение для события с указанной сигнатурой метаданных и получает маркер для этого определения события.|  
|[Метод DefineField](imetadataemit-definefield-method.md)|Создает определение для поля с указанной сигнатурой метаданных и получает маркер для этого определения поля.|  
|[Метод DefineImportMember](imetadataemit-defineimportmember-method.md)|Создает определение для члена типа, который определен в модуле за пределами текущей области, и получает маркер для этого определения ссылки.|  
|[Метод DefineImportType](imetadataemit-defineimporttype-method.md)|Создает определение для ссылки на тип, который определен в модуле за пределами текущей области, и получает маркер для этого эталонного определения.|  
|[Метод DefineMemberRef](imetadataemit-definememberref-method.md)|Создает определение для ссылки на член модуля за пределами текущей области и получает маркер для этого эталонного определения.|  
|[Метод DefineMethod](imetadataemit-definemethod-method.md)|Создает определение для метода с указанной сигнатурой и возвращает маркер в это определение метода.|  
|[Метод DefineMethodImpl](imetadataemit-definemethodimpl-method.md)|Создает определение для реализации метода, унаследованного от интерфейса, и возвращает маркер для этого определения реализации метода.|  
|[Метод DefineModuleRef](imetadataemit-definemoduleref-method.md)|Создает подпись метаданных для модуля с указанным именем.|  
|[Метод DefineNestedType](imetadataemit-definenestedtype-method.md)|Создает сигнатуру метаданных определения типа и возвращает `mdTypeDef` маркер для этого типа, кроме указания того, что определенный тип является членом типа, на который ссылается `tdEncloser` .|  
|[Метод DefineParam](imetadataemit-defineparam-method.md)|Создает определение параметра с указанной сигнатурой для метода, на который ссылается указанный токен, и получает маркер для этого определения параметра.|  
|[Метод DefinePermissionSet](imetadataemit-definepermissionset-method.md)|Создает определение для набора разрешений с указанной сигнатурой метаданных и получает маркер для этого определения набора разрешений.|  
|[Метод DefinePinvokeMap](imetadataemit-definepinvokemap-method.md)|Задает функции сигнатуры PInvoke метода, на который ссылается указанный токен.|  
|[Метод DefineProperty](imetadataemit-defineproperty-method.md)|Создает определение свойства для указанного типа с указанными `get` `set` методами доступа и и получает маркер для этого определения свойства.|  
|[Метод DefineSecurityAttributeSet](imetadataemit-definesecurityattributeset-method.md)|Создает набор разрешений безопасности для присоединения к объекту, на который ссылается указанный токен.|  
|[Метод DefineTypeDef](imetadataemit-definetypedef-method.md)|Создает определение типа для типа среды CLR и получает маркер метаданных для этого определения типа.|  
|[Метод DefineTypeRefByName](imetadataemit-definetyperefbyname-method.md)|Возвращает токен метаданных для типа, определенного в другом модуле за пределами текущей области.|  
|[Метод DefineUserString](imetadataemit-defineuserstring-method.md)|Возвращает токен метаданных для указанной литеральной строки.|  
|[Метод DeleteClassLayout](imetadataemit-deleteclasslayout-method.md)|Уничтожает сигнатуру метаданных макета класса для типа, на который ссылается указанный токен.|  
|[Метод DeleteFieldMarshal](imetadataemit-deletefieldmarshal-method.md)|Уничтожает сигнатуру метаданных упаковки PInvoke для объекта, на который ссылается указанный токен.|  
|[Метод DeletePinvokeMap](imetadataemit-deletepinvokemap-method.md)|Уничтожает метаданные сопоставления PInvoke для объекта, на который ссылается указанный токен.|  
|[Метод DeleteToken](imetadataemit-deletetoken-method.md)|Удаляет указанный токен из текущей области метаданных.|  
|[Метод GetSaveSize](imetadataemit-getsavesize-method.md)|Возвращает приблизительный двоичный размер сборки в текущей области.|  
|[Метод GetTokenFromSig](imetadataemit-gettokenfromsig-method.md)|Возвращает токен для указанной сигнатуры метаданных.|  
|[Метод GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md)|Возвращает токен метаданных для типа с указанной сигнатурой метаданных.|  
|[Метод Merge](imetadataemit-merge-method.md)|Добавляет указанную импортированную область в список объединяемых областей.|  
|[Метод MergeEnd](imetadataemit-mergeend-method.md)|Выполняет слияние в текущую область всех областей метаданных, указанных одним или несколькими ранними вызовами метода `IMetaDataEmit::Merge` .|  
|[Метод Save](imetadataemit-save-method.md)|Сохраняет все метаданные в текущей области в файле по указанному адресу.|  
|[Метод SaveToMemory](imetadataemit-savetomemory-method.md)|Сохраняет все метаданные в текущей области в указанную область памяти.|  
|[Метод SaveToStream](imetadataemit-savetostream-method.md)|Сохраняет все метаданные в текущей области в указанном `IStream` .|  
|[Метод SetClassLayout](imetadataemit-setclasslayout-method.md)|Задает или обновляет сигнатуру макета класса для типа, определенного в предыдущем вызове метода `IMetaDataEmit::DefineTypeDef` .|  
|[Метод SetCustomAttributeValue](imetadataemit-setcustomattributevalue-method.md)|Задает или обновляет значение настраиваемого атрибута, определенного при предыдущем вызове метода `IMetaDataEmit::DefineCustomAttribute` .|  
|[Метод SetEventProps](imetadataemit-seteventprops-method.md)|Задает или обновляет указанную функцию события, определенного при предыдущем вызове метода `IMetaDataEmit::DefineEvent` .|  
|[Метод SetFieldMarshal](imetadataemit-setfieldmarshal-method.md)|Задает сведения о маршалировании PInvoke для поля, возвращаемого метода или параметра метода, на который ссылается указанный токен.|  
|[Метод SetFieldProps](imetadataemit-setfieldprops-method.md)|Задает или обновляет значение по умолчанию для поля, на которое ссылается заданный токен поля.|  
|[Метод SetFieldRVA](imetadataemit-setfieldrva-method.md)|Задает значение глобальной переменной для относительного виртуального адреса поля, на которое ссылается указанный токен.|  
|[Метод SetHandler](imetadataemit-sethandler-method.md)|Задает метод, на который ссылается указанный `IUnknown` указатель, в качестве обратного вызова уведомления для повторного сопоставления токена.|  
|[Метод SetMethodImplFlags](imetadataemit-setmethodimplflags-method.md)|Задает или обновляет сигнатуру метаданных реализации унаследованного метода, на которую ссылается указанный токен.|  
|[Метод SetMethodProps](imetadataemit-setmethodprops-method.md)|Задает или обновляет компонент, хранящийся по указанному относительному виртуальному адресу метода, определенного при предыдущем вызове функции `IMetaDataEmit::DefineMethod` .|  
|[Метод SetModuleProps](imetadataemit-setmoduleprops-method.md)|Обновляет ссылки на модуль, определенный при предыдущем вызове метода `IMetaDataEmit::DefineModuleRef` .|  
|[Метод SetParamProps](imetadataemit-setparamprops-method.md)|Задает или изменяет функции параметра метода, который был определен при предыдущем вызове функции `IMetaDataEmit::DefineParam` .|  
|[Метод SetParent](imetadataemit-setparent-method.md)|Устанавливает, что указанный элемент, как определено в предыдущем вызове `IMetaDataEmit::DefineMemberRef` , является членом указанного типа, как определено в предыдущем вызове метода `IMetaDataEmit::DefineTypeDef` .|  
|[Метод SetPermissionSetProps](imetadataemit-setpermissionsetprops-method.md)|Задает или обновляет функции сигнатуры метаданных набора разрешений, определенного при предыдущем вызове метода `IMetaDataEmit::DefinePermissionSet` .|  
|[Метод SetPinvokeMap](imetadataemit-setpinvokemap-method.md)|Задает или изменяет функции сигнатуры PInvoke метода, как определено в предыдущем вызове функции `IMetaDataEmit::DefinePinvokeMap` .|  
|[Метод SetPropertyProps](imetadataemit-setpropertyprops-method.md)|Задает функции, хранимые в метаданных для свойства, определенного при предыдущем вызове метода `IMetaDataEmit::DefineProperty` .|  
|[Метод SetRVA](imetadataemit-setrva-method.md)|Задает относительный виртуальный адрес указанного метода.|  
|[Метод SetTypeDefProps](imetadataemit-settypedefprops-method.md)|Задает функции типа, определенного при предыдущем вызове метода `IMetaDataEmit::DefineTypeDef` .|  
|[Метод TranslateSigWithScope](imetadataemit-translatesigwithscope-method.md)|Импортирует сборку в текущую область и получает новую сигнатуру метаданных для Объединенной области.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **Платформа .NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы метаданных](metadata-interfaces.md)
- [Интерфейс IMetaDataEmit2](imetadataemit2-interface.md)

---
title: Интерфейс IMetaDataImport
ms.date: 03/30/2017
api_name:
- IMetaDataImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport
helpviewer_keywords:
- IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0adbbd35-5e8d-4fec-8268-dc70a07c5975
topic_type:
- apiref
ms.openlocfilehash: 0049db66d7a753488388c85e87e1f907db56c7cf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679095"
---
# <a name="imetadataimport-interface"></a>Интерфейс IMetaDataImport

Предоставляет методы для импорта существующих метаданных из переносимого исполняемого (PE) файла или другого источника, такого как библиотека типов или отдельный двоичный файл метаданных среды выполнения, а также управления этим метаданными.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CloseEnum](imetadataimport-closeenum-method.md)|Закрывает перечислитель с указанным дескриптором.|  
|[Метод CountEnum](imetadataimport-countenum-method.md)|Возвращает число элементов в перечислителе с указанным дескриптором.|  
|[Метод EnumCustomAttributes](imetadataimport-enumcustomattributes-method.md)|Перечисляет список токенов определений настраиваемых атрибутов, связанных с указанным типом или членом.|  
|[Метод EnumEvents](imetadataimport-enumevents-method.md)|Перечисляет токены определений событий для указанного токена TypeDef.|  
|[Метод EnumFields](imetadataimport-enumfields-method.md)|Перечисляет токены FieldDef для типа, на который ссылается указанный токен TypeDef.|  
|[Метод EnumFieldsWithName](imetadataimport-enumfieldswithname-method.md)|Перечисляет токены FieldDef заданного типа с указанным именем.|  
|[Метод EnumInterfaceImpls](imetadataimport-enuminterfaceimpls-method.md)|Перечисляет токены MethodDef, представляющие реализации интерфейса.|  
|[Метод EnumMemberRefs](imetadataimport-enummemberrefs-method.md)|Перечисляет токены MemberRef, представляющие члены указанного типа.|  
|[Метод EnumMembers](imetadataimport-enummembers-method.md)|Перечисляет токены MemberDef, представляющие члены указанного типа.|  
|[Метод EnumMembersWithName](imetadataimport-enummemberswithname-method.md)|Перечисляет токены MemberDef, представляющие члены указанного типа с заданным именем.|  
|[Метод EnumMethodImpls](imetadataimport-enummethodimpls-method.md)|Перечисляет токены MethodBody и MethodDeclaration, представляющие методы указанного типа.|  
|[Метод EnumMethods](imetadataimport-enummethods-method.md)|Перечисляет токены MethodDef, представляющие методы указанного типа.|  
|[Метод EnumMethodSemantics](imetadataimport-enummethodsemantics-method.md)|Перечисляет свойства и события их изменения, с которыми связан указанный метод.|  
|[Метод EnumMethodsWithName](imetadataimport-enummethodswithname-method.md)|Перечисляет методы с заданным именем, определяемые по типу, на который ссылается указанный токен TypeDef.|  
|[Метод EnumModuleRefs](imetadataimport-enummodulerefs-method.md)|Перечисляет токены ModuleRef, представляющие импортируемые модули.|  
|[Метод EnumParams](imetadataimport-enumparams-method.md)|Перечисляет токены ParamDef, представляющие параметры метода, на который ссылается указанный токен MethodDef.|  
|[Метод EnumPermissionSets](imetadataimport-enumpermissionsets-method.md)|Перечисляет разрешения для объектов в указанной области метаданных.|  
|[Метод EnumProperties](imetadataimport-enumproperties-method.md)|Перечисляет токены PropertyDef, представляющие свойства типа, на который ссылается указанный токен TypeDef.|  
|[Метод EnumSignatures](imetadataimport-enumsignatures-method.md)|Перечисляет токены Signature, представляющие отдельные подписи в текущей области.|  
|[Метод EnumTypeDefs](imetadataimport-enumtypedefs-method.md)|Перечисляет токены TypeDef, представляющие все типы в текущей области.|  
|[Метод EnumTypeRefs](imetadataimport-enumtyperefs-method.md)|Перечисляет токены TypeRef, определенные в текущей области метаданных.|  
|[Метод EnumTypeSpecs](imetadataimport-enumtypespecs-method.md)|Перечисляет токены TypeSpec, определенные в текущей области метаданных.|  
|[Метод EnumUnresolvedMethods](imetadataimport-enumunresolvedmethods-method.md)|Перечисляет токены MemberDef, представляющие неразрешенные методы в текущей области метаданных.|  
|[Метод EnumUserStrings](imetadataimport-enumuserstrings-method.md)|Перечисляет токены String, представляющие жестко заданные строки в текущей области метаданных.|  
|[Метод FindField](imetadataimport-findfield-method.md)|Возвращает токен FieldDef для поля, являющегося членом заданного типа и обладающего указанными именем и подписью метаданных.|  
|[Метод FindMember](imetadataimport-findmember-method.md)|Возвращает указатель на токен MemberDef для члена, определенного заданным типом, с указанными именем и подписью метаданных.|  
|[Метод FindMemberRef](imetadataimport-findmemberref-method.md)|Возвращает указатель на токен MemberRef для члена, определенного заданным типом, с указанными именем и подписью метаданных.|  
|[Метод FindMethod](imetadataimport-findmethod-method.md)|Возвращает указатель на токен MethodDef для метода, определенного заданным типом, с указанными именем и подписью метаданных.|  
|[Метод FindTypeDefByName](imetadataimport-findtypedefbyname-method.md)|Возвращает указатель на токен метаданных TypeDef для типа с указанным именем.|  
|[Метод FindTypeRef](imetadataimport-findtyperef-method.md)|Возвращает указатель на токен метаданных TypeRef, который ссылается на тип в заданной области поиска с указанным именем.|  
|[Метод GetClassLayout](imetadataimport-getclasslayout-method.md)|Возвращает сведения о структуре для класса, на который ссылается указанный токен TypeDef.|  
|[Метод GetCustomAttributeByName](imetadataimport-getcustomattributebyname-method.md)|Возвращает значение настраиваемого атрибута по указанному имени.|  
|[Метод GetCustomAttributeProps](imetadataimport-getcustomattributeprops-method.md)|Возвращает значение пользовательского атрибута по указанному токену метаданных.|  
|[Метод GetEventProps](imetadataimport-geteventprops-method.md)|Возвращает сведения о метаданных (включая объявленный тип, методы добавления и удаления для делегатов, а также всевозможные флаги и другие связанные с ними данные) для события, представленного указанным токеном события.|  
|[Метод GetFieldMarshal](imetadataimport-getfieldmarshal-method.md)|Возвращает указатель на машинный неуправляемый тип поля, представленного заданным токеном метаданных Field.|  
|[Метод GetFieldProps](imetadataimport-getfieldprops-method.md)|Возвращает метаданные, связанные с полем, на которое ссылается указанный токен FieldDef.|  
|[Метод GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)|Возвращает указатель на токены метаданных для типа, который реализует заданный метод, и интерфейса, который объявляет этот метод.|  
|[Метод GetMemberProps](imetadataimport-getmemberprops-method.md)|Возвращает сведения о метаданных (в том числе имя, двоичную подпись и относительный виртуальный адрес) члена типа, на который ссылается указанный токен метаданных.|  
|[Метод GetMemberRefProps](imetadataimport-getmemberrefprops-method.md)|Возвращает метаданные, связанные с членом, на который ссылается указанный токен.|  
|[Метод GetMethodProps](imetadataimport-getmethodprops-method.md)|Возвращает метаданные, связанные с методом, на который ссылается указанный токен MethodDef.|  
|[Метод GetMethodSemantics](imetadataimport-getmethodsemantics-method.md)|Возвращает указатель на взаимосвязь между методом, на который ссылается заданный токен MethodDef, и парой, состоящей из свойства и события, на которую ссылается заданный токен EventProp.|  
|[Метод GetModuleFromScope](imetadataimport-getmodulefromscope-method.md)|Возвращает указатель на токен метаданных для модуля, ссылка на который содержится в текущей области метаданных.|  
|[Метод GetModuleRefProps](imetadataimport-getmodulerefprops-method.md)|Возвращает имя модуля, на который ссылается указанный токен метаданных.|  
|[Метод GetNameFromToken](imetadataimport-getnamefromtoken-method.md)|Возвращает имя объекта, на который ссылается указанный токен метаданных, в формате UTF-8.|  
|[Метод GetNativeCallConvFromSig](imetadataimport-getnativecallconvfromsig-method.md)|Возвращает собственное соглашение о вызовах для метода, представленного заданным указателем на подпись.|  
|[Метод GetNestedClassProps](imetadataimport-getnestedclassprops-method.md)|Возвращает токен TypeDef для включающего родительского типа заданного вложенного типа.|  
|[Метод GetParamForMethodIndex](imetadataimport-getparamformethodindex-method.md)|Возвращает указатель на токен, представляющий параметр с заданным порядковым номером в последовательности параметров метода, представленного указанным токеном MethodDef.|  
|[Метод GetParamProps](imetadataimport-getparamprops-method.md)|Возвращает значения метаданных для параметра, на который ссылается указанный токен ParamDef.|  
|[Метод GetPermissionSetProps](imetadataimport-getpermissionsetprops-method.md)|Возвращает метаданные, связанные с набором разрешений System.Security.PermissionSet, который представлен указанным токеном Permission.|  
|[Метод GetPinvokeMap](imetadataimport-getpinvokemap-method.md)|Возвращает токен ModuleRef, представляющий целевую сборку вызова PInvoke.|  
|[Метод GetPropertyProps](imetadataimport-getpropertyprops-method.md)|Возвращает метаданные, связанные со свойством, представленным указанным токеном.|  
|[Метод GetRVA](imetadataimport-getrva-method.md)|Возвращает смещение относительного виртуального адреса объекта кода, представленного указанным токеном.|  
|[Метод GetScopeProps](imetadataimport-getscopeprops-method.md)|Возвращает имя и при необходимости идентификатор версии сборки или модуля в текущей области метаданных.|  
|[Метод GetSigFromToken](imetadataimport-getsigfromtoken-method.md)|Возвращает двоичную подпись метаданных, связанную с указанным токеном.|  
|[Метод GetTypeDefProps](imetadataimport-gettypedefprops-method.md)|Возвращает сведения о метаданных для типа, представленного указанным токеном TypeDef.|  
|[Метод GetTypeRefProps](imetadataimport-gettyperefprops-method.md)|Возвращает метаданные, связанные с типом, на который ссылается указанный токен TypeRef.|  
|[Метод GetTypeSpecFromToken](imetadataimport-gettypespecfromtoken-method.md)|Возвращает двоичную подпись метаданных для спецификации типа, представленного указанным токеном.|  
|[Метод GetUserString](imetadataimport-getuserstring-method.md)|Получает строку литералов, представленную указанным токеном метаданных.|  
|[Метод IsGlobal](imetadataimport-isglobal-method.md)|Возвращает значение, указывающее на наличие глобальной области у поля, метода или типа, представленного заданным токеном метаданных.|  
|[Метод IsValidToken](imetadataimport-isvalidtoken-method.md)|Возвращает значение, указывающее, содержится ли в заданном токене допустимая ссылка на объект кода.|  
|[Метод ResetEnum](imetadataimport-resetenum-method.md)|Возвращает заданный перечислитель в указанную позицию.|  
|[Метод ResolveTypeRef](imetadataimport-resolvetyperef-method.md)|Возвращает сведения о типе, на который ссылается указанный токен TypeRef.|  
  
## <a name="remarks"></a>Комментарии  

 По своей структуре интерфейс `IMetaDataImport` предназначен в первую очередь для использования средствами и службами, которые будут импортировать сведения о типах (например, средства разработки) или управлять компонентами развертывания (например, службы разрешения или активации). Методы интерфейса `IMetaDataImport` делятся по задачам на следующие категории:  
  
- перечисление коллекций элементов в области метаданных;  
  
- поиск элементов с определенным набором характеристик;  
  
- получение свойств указанного элемента;  
  
- методы Get предназначены специально для возврата свойств с одним значением для элемента метаданных. Если свойство ссылается на другой элемент, возвращается токен этого элемента. Любой тип ввода указателя может иметь значение NULL, свидетельствующее о том, что определенное значение не запрашивается. Для получения свойств, которые по сути являются объектами коллекции (например, коллекции интерфейсов, реализуемых классом), используются методы перечисления.  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** COR. h  
  
 **Библиотека:** Используется в качестве ресурса в MsCorEE.dll  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейсы метаданных](metadata-interfaces.md)
- [Интерфейс IMetaDataImport2](imetadataimport2-interface.md)

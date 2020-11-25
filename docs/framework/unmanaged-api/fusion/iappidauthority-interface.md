---
title: Интерфейс IAppIdAuthority
ms.date: 03/30/2017
api_name:
- IAppIdAuthority
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAppIdAuthority
helpviewer_keywords:
- IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type:
- apiref
ms.openlocfilehash: a344f2ab5d9a7aa92018c47ee7a162cd1721aeb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732116"
---
# <a name="iappidauthority-interface"></a>Интерфейс IAppIdAuthority

Предоставляет методы, создающие и сравнивающие ключи для удостоверений приложений и ссылок.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|Возвращает значение, указывающее, равны ли два указанных экземпляра [IDefinitionAppId](idefinitionappid-interface.md) . Можно передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION, чтобы игнорировать соответствующие сведения о версии.|  
|`IAppIdAuthority::AreReferencesEqual`|Возвращает значение, указывающее, равны ли два указанных экземпляра [иреференцеаппид](ireferenceappid-interface.md) . Можно передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION, чтобы игнорировать соответствующие сведения о версии.|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|Возвращает значение, указывающее, равны ли два указанных строковые определения. Можно передать значение флага IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION, чтобы игнорировать соответствующие сведения о версии.|  
|`IAppIdAuthority::AreTextualReferencesEqual`|Возвращает значение, указывающее, равны ли две указанные строковые ссылки. Можно передать значение флага IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION, чтобы игнорировать соответствующие сведения о версии.|  
|`IAppIdAuthority::CreateDefinition`|Возвращает указатель интерфейса на вновь созданный `IDefinitionAppId` экземпляр, представляющий сборку в текущей области.|  
|`IAppIdAuthority::CreateReference`|Возвращает указатель интерфейса на только что созданный объект `IReferenceAppId` , представляющий сборку в текущей области.|  
|`IAppIdAuthority::DefinitionToText`|Возвращает строковую версию указанного объекта `IDefinitionAppId` , используя указанные значения флага.|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|Возвращает значение, указывающее, представляет ли заданную `IDefinitionAppId` и одну и ту `IReferenceAppId` же сборку.|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|Возвращает значение, указывающее, представляет ли указанная строка определения и ссылочную строку одну и ту же сборку.|  
|`IAppIdAuthority::GenerateDefinitionKey`|Возвращает строковый ключ, представляющий указанный `IDefinitionAppId` экземпляр.|  
|`IAppIdAuthority::GenerateReferenceKey`|Возвращает строковый ключ, представляющий указанный `IReferenceAppId` экземпляр.|  
|`IAppIdAuthority::HashDefinition`|Возвращает хэш-ключ для указанного `IDefinitionAppId` экземпляра.|  
|`IAppIdAuthority::HashReference`|Возвращает хэш-ключ для указанного `IReferenceAppId` экземпляра.|  
|`IAppIdAuthority::ReferenceToText`|Возвращает строковую версию указанного объекта `IReferenceAppId` , используя указанные значения флага.|  
|`IAppIdAuthority::TextToDefinition`|Возвращает указатель интерфейса на `IDefinitionAppId` экземпляр, представляющий сборку, на которую ссылается указанный ключ строки.|  
|`IAppIdAuthority::TextToReference`|Возвращает указатель интерфейса на `IReferenceAppId` экземпляр, представляющий сборку, на которую ссылается указанный ключ строки.|  
  
## <a name="requirements"></a>Требования  

 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Изоляция. h  
  
 **.NET Framework версии:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Fusion-интерфейсы](fusion-interfaces.md)

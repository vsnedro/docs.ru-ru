---
title: <issuerNameRegistry>
ms.date: 03/30/2017
ms.assetid: 58b39d12-c953-40c4-88af-d7eb3343ca28
author: BrucePerlerMS
ms.openlocfilehash: 209e702da80f2569f2b6c068f50f1af4489157f6
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "70251967"
---
# \<issuerNameRegistry>
Настраивает реестр имен издателя, используемый обработчиками в коллекции обработчиков маркеров.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerNameRegistry>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerNameRegistry type=xs:string>  
          <optionalCustomConfigurationElements />  
        </issuerNameRegistry>  
      </securityTokenHandlerConfiguration>  
    </securityTokenHandlers>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|type|Тип, производный от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса. Дополнительные сведения о том, как указать пользовательский параметр `type` , см. в разделе [ссылки на пользовательские типы].|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<trustedIssuers>](trustedissuers.md)|Если `type` атрибут указывает реестр имен издателя на основе конфигурации ( <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класс), [\<trustedIssuers>](trustedissuers.md) необходимо указать элемент. [\<trustedIssuers>](trustedissuers.md)Элемент может принимать `<add>` элементы, `<clear>` или `<remove>` как дочерние элементы.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Примечания  
 Все маркеры издателя проверяются с помощью реестра имени издателя. Это объект, производный от <xref:System.IdentityModel.Tokens.IssuerNameRegistry> класса. Реестр имен издателей используется для связывания назначенного имени с криптографическим материалом, необходимым для проверки подписей маркеров, созданных соответствующим издателем. В реестре имен издателей хранится список издателей, которым доверяет приложение проверяющей стороны (RP). Тип реестра имени издателя указывается с помощью `type` атрибута. `<issuerNameRegistry>`Элемент может иметь один или несколько дочерних элементов, которые предоставляют конфигурацию для указанного типа. Вы предоставляете логику, которая обрабатывает эти дочерние элементы, переопределяя <xref:System.IdentityModel.Tokens.IssuerNameRegistry.LoadCustomConfiguration%2A> метод.  
  
 WIF предоставляет один тип реестра имени поставщика из поля, <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry> класс. Этот класс использует набор сертификатов доверенных издателей, указанных в конфигурации. Для этого требуется дочерний элемент конфигурации, `<trustedIssuers>` в котором настроена Коллекция сертификатов доверенных издателей. Доверенные сертификаты указываются с помощью формы отпечатка сертификата в кодировке ASN. 1, которые добавляются или удаляются из коллекции с помощью `<add>` `<clear>` элементов, или `<remove>` .  
  
 `<issuerNameRegistry>`Элемент представлен <xref:System.IdentityModel.Configuration.IssuerNameRegistryElement> классом.  
  
> [!NOTE]
> Указание `<issuerNameRegistry>` элемента в качестве дочернего элемента [\<identityConfiguration>](identityconfiguration.md) элемента является устаревшим, но по-прежнему поддерживается для обратной совместимости. Параметры `<securityTokenHandlerConfiguration>` элемента переопределяют их для `<identityConfiguration>` элемента.  
  
## <a name="example"></a>Пример  
 В следующем коде XML показано, как указать реестр имен поставщиков на основе конфигурации.  
  
```xml  
<issuerNameRegistry type="System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry, System.IdentityModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089">  
  <trustedIssuers>  
    <add thumbprint="9B74CB … 1EF40D0" name="LocalSTS" />  
  </trustedIssuers>  
</issuerNameRegistry>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Tokens.IssuerNameRegistry>
- <xref:System.IdentityModel.Tokens.ConfigurationBasedIssuerNameRegistry>

---
description: 'Дополнительные сведения: <issuerTokenResolver>'
title: <issuerTokenResolver>
ms.date: 03/30/2017
ms.assetid: f74392f6-3f5b-4880-bd8a-3a9130d31e65
author: BrucePerlerMS
ms.openlocfilehash: 535b6f098e168a198eb0949d6baba6659e5140db
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99664097"
---
# \<issuerTokenResolver>

Регистрирует сопоставитель маркеров издателя, используемый обработчиками в коллекции обработчиков маркеров. Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel>**](system-identitymodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<identityConfiguration>**](identityconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlers>**](securitytokenhandlers.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<securityTokenHandlerConfiguration>**](securitytokenhandlerconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<issuerTokenResolver>**  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <securityTokenHandlers>  
      <securityTokenHandlerConfiguration>  
        <issuerTokenResolver type=xs:string>  
        </issuerTokenResolver>  
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
|type|Указывает тип сопоставителя маркеров издателя. Должен быть либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver> классом, либо типом, производным от <xref:System.IdentityModel.Tokens.IssuerTokenResolver> класса. Обязательный элемент.|  
  
### <a name="child-elements"></a>Дочерние элементы  

 None  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<securityTokenHandlerConfiguration>](securitytokenhandlerconfiguration.md)|Предоставляет конфигурацию для коллекции обработчиков маркеров безопасности.|  
  
## <a name="remarks"></a>Remarks  

 Сопоставитель токенов издателя используется для разрешения маркера подписывания входящих токенов и сообщений. Он используется для получения криптографического материала, используемого для проверки подписи. Необходимо указать `type` атрибут. Указанный тип может быть либо либо <xref:System.IdentityModel.Tokens.IssuerTokenResolver> пользовательским типом, производным от <xref:System.IdentityModel.Tokens.IssuerTokenResolver> класса.  
  
 Некоторые обработчики маркеров позволяют задавать параметры сопоставителя маркеров издателя в конфигурации. Параметры отдельных обработчиков маркеров переопределяют те, которые указаны в коллекции обработчика маркеров безопасности.  
  
> [!NOTE]
> Указание `<issuerTokenResolver>` элемента в качестве дочернего элемента [\<identityConfiguration>](identityconfiguration.md) элемента является устаревшим, но по-прежнему поддерживается для обратной совместимости. Параметры `<securityTokenHandlerConfiguration>` элемента переопределяют их для `<identityConfiguration>` элемента.  
  
## <a name="example"></a>Пример  

 В следующем коде XML показана конфигурация для сопоставителя маркеров издателя, основанного на пользовательском классе, производном от <xref:System.IdentityModel.Tokens.IssuerTokenResolver> . Сопоставитель токенов поддерживает словарь пар ключей аудитории, которые инициализируются из настраиваемого элемента конфигурации ( `<AddAudienceKeyPair>` ), определенного для класса. Класс переопределяет <xref:System.IdentityModel.Selectors.SecurityTokenResolver.LoadCustomConfiguration%2A> метод для обработки этого элемента. Переопределение показано в следующем примере. Однако методы, которые он вызывает, не отображаются для краткости. Полный пример см `CustomToken` . в примере.  
  
```xml  
<issuerTokenResolver type="SimpleWebToken.CustomIssuerTokenResolver, SimpleWebToken">  
  <AddAudienceKeyPair  symmetricKey="wAVkldQiFypTQ+kdNdGWCYCHRcee8XmXxOvgmak8vSY=" audience="http://localhost:19851/" />  
</issuerTokenResolver>  
```  
  
## <a name="example"></a>Пример
  
```csharp
public override void LoadCustomConfiguration(System.Xml.XmlNodeList nodelist)  
{  
    foreach (XmlNode node in nodelist)  
    {  
        XmlDictionaryReader rdr = XmlDictionaryReader.CreateDictionaryReader(new XmlTextReader(new StringReader(node.OuterXml)));  
        rdr.MoveToContent();  
  
        string symmetricKey = rdr.GetAttribute("symmetricKey");  
        string audience = rdr.GetAttribute("audience");  
  
        this.AddAudienceKeyPair(audience, symmetricKey);  
    }  
}  
```
  
## <a name="see-also"></a>См. также

- <xref:System.IdentityModel.Tokens.IssuerTokenResolver>

---
title: <persistableType>
ms.date: 03/30/2017
ms.assetid: e5425fe6-523a-4076-aab4-2c2515b1d830
ms.openlocfilehash: 6425b21fe50865beb7bb2876ea478b415fbe3944
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91181522"
---
# \<persistableType>

<span data-ttu-id="ea326-101">Задает все восстанавливаемые типы.</span><span class="sxs-lookup"><span data-stu-id="ea326-101">Specifies all the persistable types.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContracts>**](comcontracts.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<comContract>**](comcontract.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<persistableTypes>**](persistabletypes.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<persistableType>**  
  
## <a name="syntax"></a><span data-ttu-id="ea326-102">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ea326-102">Syntax</span></span>  
  
```xml  
<comContracts>
  <comContract>
    <persistableTypes>
      <persistableType id="String"
                       name="String">
      </persistableType>
    </persistableTypes>
  </comContract>
</comContracts>
```  
  
## <a name="type"></a><span data-ttu-id="ea326-103">Type</span><span class="sxs-lookup"><span data-stu-id="ea326-103">Type</span></span>  

 `Type`  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ea326-104">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="ea326-104">Attributes and Elements</span></span>  

 <span data-ttu-id="ea326-105">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="ea326-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ea326-106">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="ea326-106">Attributes</span></span>  
  
|<span data-ttu-id="ea326-107">Атрибут</span><span class="sxs-lookup"><span data-stu-id="ea326-107">Attribute</span></span>|<span data-ttu-id="ea326-108">Описание</span><span class="sxs-lookup"><span data-stu-id="ea326-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ea326-109">идентификатор</span><span class="sxs-lookup"><span data-stu-id="ea326-109">id</span></span>|<span data-ttu-id="ea326-110">Обязательный атрибут, содержащий строку, которая задает уникальный идентификатор для восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="ea326-110">A required attribute that contains a string that specifies a unique identifier for a persistable type.</span></span>|  
|<span data-ttu-id="ea326-111">name</span><span class="sxs-lookup"><span data-stu-id="ea326-111">name</span></span>|<span data-ttu-id="ea326-112">Необязательный атрибут, содержащий строку, которая задает имя восстанавливаемого типа.</span><span class="sxs-lookup"><span data-stu-id="ea326-112">An optional attribute that contains a string that specifies the name of the persistable type.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ea326-113">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="ea326-113">Child Elements</span></span>  

 <span data-ttu-id="ea326-114">Нет</span><span class="sxs-lookup"><span data-stu-id="ea326-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ea326-115">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="ea326-115">Parent Elements</span></span>  
  
|<span data-ttu-id="ea326-116">Элемент</span><span class="sxs-lookup"><span data-stu-id="ea326-116">Element</span></span>|<span data-ttu-id="ea326-117">Описание</span><span class="sxs-lookup"><span data-stu-id="ea326-117">Description</span></span>|  
|-------------|-----------------|  
|[\<persistableTypes>](persistabletypes.md)|<span data-ttu-id="ea326-118">Коллекция элементов `persistableType`.</span><span class="sxs-lookup"><span data-stu-id="ea326-118">A collection of `persistableType` elements.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ea326-119">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ea326-119">See also</span></span>

- <xref:System.ServiceModel.Configuration.ComPersistableTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ComPersistableTypeElement>
- [\<comContracts>](comcontracts.md)
- [<span data-ttu-id="ea326-120">Интеграция с приложениями COM+</span><span class="sxs-lookup"><span data-stu-id="ea326-120">Integrating with COM+ Applications</span></span>](../../../wcf/feature-details/integrating-with-com-plus-applications.md)
- [<span data-ttu-id="ea326-121">Практическое руководство. Настройка параметров службы COM+</span><span class="sxs-lookup"><span data-stu-id="ea326-121">How to: Configure COM+ Service Settings</span></span>](../../../wcf/feature-details/how-to-configure-com-service-settings.md)

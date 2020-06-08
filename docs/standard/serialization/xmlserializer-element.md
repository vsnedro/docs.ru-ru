---
title: Элемент <xmlSerializer>
description: Элемент <xmlSerializer> указывает, выполнена ли дополнительная проверка хода выполнения XmlSerializer.
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 667d59f7eb0d1c7682afcdda584cc5b0ca2da802
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "84288931"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="8358d-103">Элемент \<xmlSerializer></span><span class="sxs-lookup"><span data-stu-id="8358d-103">\<xmlSerializer> Element</span></span>
<span data-ttu-id="8358d-104">Указывает, выполнена ли дополнительная проверка хода выполнения <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8358d-104">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a><span data-ttu-id="8358d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8358d-105">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8358d-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="8358d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="8358d-107">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="8358d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8358d-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="8358d-108">Attributes</span></span>  
  
|<span data-ttu-id="8358d-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="8358d-109">Attribute</span></span>|<span data-ttu-id="8358d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="8358d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8358d-111">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="8358d-111">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="8358d-112">Указывает, выполнена ли проверка хода выполнения <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="8358d-112">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="8358d-113">Присвойте атрибуту значение "true" или "false".</span><span class="sxs-lookup"><span data-stu-id="8358d-113">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="8358d-114">Значение по умолчанию - "true".</span><span class="sxs-lookup"><span data-stu-id="8358d-114">The default is "true".</span></span>|  
|<span data-ttu-id="8358d-115">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="8358d-115">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="8358d-116">Укажите, следует ли объекту <xref:System.Xml.Serialization.XmlSerializer> использовать установленную сериализацию прежней версии, которая создает сборки путем написания кода на C# в файле и компиляции его в сборку.</span><span class="sxs-lookup"><span data-stu-id="8358d-116">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="8358d-117">Значение по умолчанию — **false**.</span><span class="sxs-lookup"><span data-stu-id="8358d-117">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="8358d-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="8358d-118">Child Elements</span></span>  
 <span data-ttu-id="8358d-119">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="8358d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="8358d-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="8358d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="8358d-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="8358d-121">Element</span></span>|<span data-ttu-id="8358d-122">Описание</span><span class="sxs-lookup"><span data-stu-id="8358d-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="8358d-123">\<system.xml.serialization> Элемент</span><span class="sxs-lookup"><span data-stu-id="8358d-123">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)|<span data-ttu-id="8358d-124">Содержит параметры конфигурации для классов <xref:System.Xml.Serialization.XmlSerializer> и <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="8358d-124">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8358d-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="8358d-125">Remarks</span></span>  
 <span data-ttu-id="8358d-126">По умолчанию <xref:System.Xml.Serialization.XmlSerializer> обеспечивает дополнительный уровень безопасности в отношении возможных атак типа "отказ в обслуживании" во время десериализации ненадежных данных.</span><span class="sxs-lookup"><span data-stu-id="8358d-126">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="8358d-127">Такие атаки отслеживаются путем определения бесконечных циклов во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="8358d-127">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="8358d-128">Если обнаруживается такое состояние, выдается исключение со следующим сообщением: "Произошла внутренняя ошибка: сбой десериализации при перемещении по базовому потоку".</span><span class="sxs-lookup"><span data-stu-id="8358d-128">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="8358d-129">Такое сообщение еще не означает, что система подвергается атаке типа "отказ в обслуживании".</span><span class="sxs-lookup"><span data-stu-id="8358d-129">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="8358d-130">В редких случаях механизм определения бесконечного цикла сообщает о ложном положительном результате, и выдается исключение для допустимых входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="8358d-130">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="8358d-131">Если обнаружится, что некоторые допустимые сообщения приложения отклоняются из-за использования такого дополнительного уровня защиты, задайте атрибут **checkDeserializeAdvances** со значением false.</span><span class="sxs-lookup"><span data-stu-id="8358d-131">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="8358d-132">Пример</span><span class="sxs-lookup"><span data-stu-id="8358d-132">Example</span></span>  
 <span data-ttu-id="8358d-133">В приведенном ниже примере кода атрибут **checkDeserializeAdvances** задан как false.</span><span class="sxs-lookup"><span data-stu-id="8358d-133">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8358d-134">См. также</span><span class="sxs-lookup"><span data-stu-id="8358d-134">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="8358d-135">\<system.xml.serialization> Элемент</span><span class="sxs-lookup"><span data-stu-id="8358d-135">\<system.xml.serialization> Element</span></span>](system-xml-serialization-element.md)
- [<span data-ttu-id="8358d-136">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="8358d-136">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)

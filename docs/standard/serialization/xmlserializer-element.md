---
title: Элемент <xmlSerializer>
description: Элемент <xmlSerializer> указывает, выполнена ли дополнительная проверка хода выполнения XmlSerializer.
ms.date: 03/30/2017
helpviewer_keywords:
- <xmlSerializer> element
- XML serialization, configuration
- xmlSerializer element
ms.assetid: d129d10c-3eb7-45d9-8098-5fa853825e47
ms.openlocfilehash: 68037959893ec307a896ea86d21e40a9d7aa824c
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "83380021"
---
# <a name="xmlserializer-element"></a><span data-ttu-id="bf272-103">Элемент \<xmlSerializer></span><span class="sxs-lookup"><span data-stu-id="bf272-103">\<xmlSerializer> Element</span></span>
<span data-ttu-id="bf272-104">Указывает, выполнена ли дополнительная проверка хода выполнения <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="bf272-104">Specifies whether an additional check of progress of the <xref:System.Xml.Serialization.XmlSerializer> is done.</span></span>  
  
 <span data-ttu-id="bf272-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="bf272-105">\<configuration></span></span>  
<span data-ttu-id="bf272-106">\<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="bf272-106">\<system.xml.serialization></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf272-107">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bf272-107">Syntax</span></span>  
  
```xml  
<xmlSerializer checkDeserializerAdvance = "true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bf272-108">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="bf272-108">Attributes and Elements</span></span>  
 <span data-ttu-id="bf272-109">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="bf272-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bf272-110">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="bf272-110">Attributes</span></span>  
  
|<span data-ttu-id="bf272-111">Атрибут</span><span class="sxs-lookup"><span data-stu-id="bf272-111">Attribute</span></span>|<span data-ttu-id="bf272-112">Описание</span><span class="sxs-lookup"><span data-stu-id="bf272-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bf272-113">**checkDeserializeAdvances**</span><span class="sxs-lookup"><span data-stu-id="bf272-113">**checkDeserializeAdvances**</span></span>|<span data-ttu-id="bf272-114">Указывает, выполнена ли проверка хода выполнения <xref:System.Xml.Serialization.XmlSerializer>.</span><span class="sxs-lookup"><span data-stu-id="bf272-114">Specifies whether the progress of the <xref:System.Xml.Serialization.XmlSerializer> is checked.</span></span> <span data-ttu-id="bf272-115">Присвойте атрибуту значение "true" или "false".</span><span class="sxs-lookup"><span data-stu-id="bf272-115">Set the attribute to "true" or "false".</span></span> <span data-ttu-id="bf272-116">Значение по умолчанию - "true".</span><span class="sxs-lookup"><span data-stu-id="bf272-116">The default is "true".</span></span>|  
|<span data-ttu-id="bf272-117">**useLegacySerializationGeneration**</span><span class="sxs-lookup"><span data-stu-id="bf272-117">**useLegacySerializationGeneration**</span></span>|<span data-ttu-id="bf272-118">Укажите, следует ли объекту <xref:System.Xml.Serialization.XmlSerializer> использовать установленную сериализацию прежней версии, которая создает сборки путем написания кода на C# в файле и компиляции его в сборку.</span><span class="sxs-lookup"><span data-stu-id="bf272-118">Specifies whether the <xref:System.Xml.Serialization.XmlSerializer> uses legacy serialization generation which generates assemblies by writing C# code to a file and then compiling it to an assembly.</span></span> <span data-ttu-id="bf272-119">Значение по умолчанию — **false**.</span><span class="sxs-lookup"><span data-stu-id="bf272-119">The default is **false**.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bf272-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="bf272-120">Child Elements</span></span>  
 <span data-ttu-id="bf272-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="bf272-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bf272-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="bf272-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bf272-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="bf272-123">Element</span></span>|<span data-ttu-id="bf272-124">Описание</span><span class="sxs-lookup"><span data-stu-id="bf272-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bf272-125">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="bf272-125">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)|<span data-ttu-id="bf272-126">Содержит параметры конфигурации для классов <xref:System.Xml.Serialization.XmlSerializer> и <xref:System.Xml.Serialization.XmlSchemaImporter>.</span><span class="sxs-lookup"><span data-stu-id="bf272-126">Contains configuration settings for the <xref:System.Xml.Serialization.XmlSerializer> and <xref:System.Xml.Serialization.XmlSchemaImporter> classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bf272-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="bf272-127">Remarks</span></span>  
 <span data-ttu-id="bf272-128">По умолчанию <xref:System.Xml.Serialization.XmlSerializer> обеспечивает дополнительный уровень безопасности в отношении возможных атак типа "отказ в обслуживании" во время десериализации ненадежных данных.</span><span class="sxs-lookup"><span data-stu-id="bf272-128">By default, the <xref:System.Xml.Serialization.XmlSerializer> provides an additional layer of security against potential denial of service attacks when deserializing untrusted data.</span></span> <span data-ttu-id="bf272-129">Такие атаки отслеживаются путем определения бесконечных циклов во время десериализации.</span><span class="sxs-lookup"><span data-stu-id="bf272-129">It does so by attempting to detect infinite loops during deserialization.</span></span> <span data-ttu-id="bf272-130">Если обнаруживается такое состояние, выдается исключение со следующим сообщением: "Произошла внутренняя ошибка: сбой десериализации при перемещении по базовому потоку".</span><span class="sxs-lookup"><span data-stu-id="bf272-130">If such a condition is detected, an exception is thrown with the following message: "Internal error: deserialization failed to advance over underlying stream."</span></span>  
  
 <span data-ttu-id="bf272-131">Такое сообщение еще не означает, что система подвергается атаке типа "отказ в обслуживании".</span><span class="sxs-lookup"><span data-stu-id="bf272-131">Receiving this message does not necessarily indicate that a denial of service attack is in progress.</span></span> <span data-ttu-id="bf272-132">В редких случаях механизм определения бесконечного цикла сообщает о ложном положительном результате, и выдается исключение для допустимых входящих сообщений.</span><span class="sxs-lookup"><span data-stu-id="bf272-132">In some rare circumstances, the infinite loop detection mechanism produces a false positive and the exception is thrown for a legitimate incoming message.</span></span> <span data-ttu-id="bf272-133">Если обнаружится, что некоторые допустимые сообщения приложения отклоняются из-за использования такого дополнительного уровня защиты, задайте атрибут **checkDeserializeAdvances** со значением false.</span><span class="sxs-lookup"><span data-stu-id="bf272-133">If you find that in your particular application legitimate messages are being rejected by this extra layer of protection, set **checkDeserializeAdvances** attribute to "false".</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf272-134">Пример</span><span class="sxs-lookup"><span data-stu-id="bf272-134">Example</span></span>  
 <span data-ttu-id="bf272-135">В приведенном ниже примере кода атрибут **checkDeserializeAdvances** задан как false.</span><span class="sxs-lookup"><span data-stu-id="bf272-135">The following code example sets the **checkDeserializeAdvances** attribute to "false".</span></span>  
  
```xml  
<configuration>  
  <system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
  </system.xml.serialization>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bf272-136">См. также</span><span class="sxs-lookup"><span data-stu-id="bf272-136">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="bf272-137">Элемент \<system.xml.serialization></span><span class="sxs-lookup"><span data-stu-id="bf272-137">\<system.xml.serialization> Element</span></span>](../../../docs/standard/serialization/system-xml-serialization-element.md)
- [<span data-ttu-id="bf272-138">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="bf272-138">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)

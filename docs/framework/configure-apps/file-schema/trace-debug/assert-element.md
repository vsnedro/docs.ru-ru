---
title: Элемент <assert>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/assert
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assert
helpviewer_keywords:
- <assert> element
- assert element
ms.assetid: ef4c3229-b151-4d85-8091-e6456af9b935
ms.openlocfilehash: f3c1a1670139a8262dea449bfff99c7c1c19f088
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088945"
---
# <a name="assert-element"></a><span data-ttu-id="b7831-102">Элемент \<assert></span><span class="sxs-lookup"><span data-stu-id="b7831-102">\<assert> Element</span></span>
<span data-ttu-id="b7831-103">Определяет, должно ли выводиться окно сообщения при вызове метода <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>. Кроме того, задает имя файла, в который записываются сообщения.</span><span class="sxs-lookup"><span data-stu-id="b7831-103">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assert>**

## <a name="syntax"></a><span data-ttu-id="b7831-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b7831-104">Syntax</span></span>  
  
```xml  
<assert assertuienabled="true|false" logfilename="file name"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7831-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b7831-105">Attributes and Elements</span></span>  
 <span data-ttu-id="b7831-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b7831-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7831-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b7831-107">Attributes</span></span>  
  
|<span data-ttu-id="b7831-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b7831-108">Attribute</span></span>|<span data-ttu-id="b7831-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="b7831-109">Description</span></span>|  
|---------------|-----------------|  
|`assertuienabled`|<span data-ttu-id="b7831-110">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b7831-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b7831-111">Указывает, следует ли отображать окно сообщения, если метод **Debug. Assert** возвращает **значение false**.</span><span class="sxs-lookup"><span data-stu-id="b7831-111">Specifies whether to display a message box when the **Debug.Assert** method evaluates to **false**.</span></span>|  
|`logfilename`|<span data-ttu-id="b7831-112">Необязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="b7831-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b7831-113">Указывает имя файла, в который будет записано сообщение, если **Debug. Assert** имеет значение **false**.</span><span class="sxs-lookup"><span data-stu-id="b7831-113">Specifies the name of the file to write the message to if **Debug.Assert** evaluates to **false**.</span></span>|  
  
## <a name="assertuienabled-attribute"></a><span data-ttu-id="b7831-114">Атрибут ассертуиенаблед</span><span class="sxs-lookup"><span data-stu-id="b7831-114">assertuienabled Attribute</span></span>  
  
|<span data-ttu-id="b7831-115">Значение</span><span class="sxs-lookup"><span data-stu-id="b7831-115">Value</span></span>|<span data-ttu-id="b7831-116">Описание</span><span class="sxs-lookup"><span data-stu-id="b7831-116">Description</span></span>|  
|-----------|-----------------|  
|`true`|<span data-ttu-id="b7831-117">Отображает окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="b7831-117">Displays the message box.</span></span> <span data-ttu-id="b7831-118">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b7831-118">This is the default.</span></span>|  
|`false`|<span data-ttu-id="b7831-119">Не отображает окно сообщения.</span><span class="sxs-lookup"><span data-stu-id="b7831-119">Does not display the message box.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7831-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b7831-120">Child Elements</span></span>  
 <span data-ttu-id="b7831-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b7831-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7831-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b7831-122">Parent Elements</span></span>  
  
|<span data-ttu-id="b7831-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="b7831-123">Element</span></span>|<span data-ttu-id="b7831-124">Описание</span><span class="sxs-lookup"><span data-stu-id="b7831-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b7831-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b7831-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b7831-126">Задает прослушиватели трассировки, собирающие, хранящие и маршрутизирующие сообщения, а также уровень, на котором установлен ключ трассировки.</span><span class="sxs-lookup"><span data-stu-id="b7831-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7831-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="b7831-127">Remarks</span></span>  
 <span data-ttu-id="b7831-128">Оба атрибута в **\<assert>** элементе являются необязательными.</span><span class="sxs-lookup"><span data-stu-id="b7831-128">Both attributes in the **\<assert>** element are optional.</span></span> <span data-ttu-id="b7831-129">Можно отключить окна сообщений, не указывая файл для записи в него, или указать файл для записи сообщений при включении входящих в него окон сообщений.</span><span class="sxs-lookup"><span data-stu-id="b7831-129">You can disable message boxes without specifying a file to write the messages to, or you can specify a file to write messages to while leaving message boxes enabled.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7831-130">Пример</span><span class="sxs-lookup"><span data-stu-id="b7831-130">Example</span></span>  
 <span data-ttu-id="b7831-131">В следующем примере показано, как отключить отображение окон сообщений при вызове **Debug. Assert** и записи сообщений в `c:\log.txt` .</span><span class="sxs-lookup"><span data-stu-id="b7831-131">The following example shows how to disable displaying message boxes when you call **Debug.Assert** and write the messages to `c:\log.txt`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <assert assertuienabled="false" logfilename="c:\log.txt"/>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b7831-132">См. также</span><span class="sxs-lookup"><span data-stu-id="b7831-132">See also</span></span>

- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="b7831-133">Схема параметров трассировки и отладки</span><span class="sxs-lookup"><span data-stu-id="b7831-133">Trace and Debug Settings Schema</span></span>](index.md)

---
title: Элемент <Crst_DisableSpinWait>
ms.date: 04/18/2019
f1_keywords:
- Crst_DisableSpinWait
helpviewer_keywords:
- Crst_DisableSpinWait element
ms.openlocfilehash: 0683081183081e249b2a9c89e1a6a15f638fb339
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73117642"
---
# <a name="crst_disablespinwait-element"></a><span data-ttu-id="f307c-102">\<Crst_DisableSpinWait> - элемент</span><span class="sxs-lookup"><span data-stu-id="f307c-102">\<Crst_DisableSpinWait> element</span></span>

<span data-ttu-id="f307c-103">Указывает, следует ли отключать режим ожидания для критической секции, если это не так.</span><span class="sxs-lookup"><span data-stu-id="f307c-103">Specifies whether to disable spin-waiting for a critical section when contended.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<Crst_DisableSpinWait>**  
  
## <a name="syntax"></a><span data-ttu-id="f307c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f307c-104">Syntax</span></span>  
  
```xml  
<Crst_DisableSpinWait enabled="true | false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f307c-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f307c-105">Attributes and Elements</span></span>

<span data-ttu-id="f307c-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f307c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f307c-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f307c-107">Attributes</span></span>  
  
|<span data-ttu-id="f307c-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f307c-108">Attribute</span></span>|<span data-ttu-id="f307c-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="f307c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f307c-110">**доступной**</span><span class="sxs-lookup"><span data-stu-id="f307c-110">**enabled**</span></span>|<span data-ttu-id="f307c-111">Указывает, отключен ли режим ожидания для критических разделов, если они не включены.</span><span class="sxs-lookup"><span data-stu-id="f307c-111">Specifies whether spin-waiting for critical sections when they are contended is disabled.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="f307c-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="f307c-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="f307c-113">Значение</span><span class="sxs-lookup"><span data-stu-id="f307c-113">Value</span></span>|<span data-ttu-id="f307c-114">Описание</span><span class="sxs-lookup"><span data-stu-id="f307c-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="f307c-115">1</span><span class="sxs-lookup"><span data-stu-id="f307c-115">1</span></span>|<span data-ttu-id="f307c-116">Отключите режим ожидания, если критическая секция не может быть получена.</span><span class="sxs-lookup"><span data-stu-id="f307c-116">Disable spin-waiting when a critical section cannot be acquired.</span></span>|  
|<span data-ttu-id="f307c-117">0</span><span class="sxs-lookup"><span data-stu-id="f307c-117">0</span></span>|<span data-ttu-id="f307c-118">Не отключайте режим ожидания, если критическая секция не может быть получена.</span><span class="sxs-lookup"><span data-stu-id="f307c-118">Do not disable spin-waiting when a critical section cannot be acquired.</span></span> <span data-ttu-id="f307c-119">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f307c-119">This is the default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f307c-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f307c-120">Child Elements</span></span>  
 <span data-ttu-id="f307c-121">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="f307c-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f307c-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f307c-122">Parent Elements</span></span>  
  
|<span data-ttu-id="f307c-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="f307c-123">Element</span></span>|<span data-ttu-id="f307c-124">Описание</span><span class="sxs-lookup"><span data-stu-id="f307c-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f307c-125">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f307c-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="f307c-126">Содержит сведения о различных параметрах конфигурации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="f307c-126">Contains information about various runtime configuration settings.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f307c-127">Пример</span><span class="sxs-lookup"><span data-stu-id="f307c-127">Example</span></span>  

<span data-ttu-id="f307c-128">В следующем примере отключается ожидание в критических разделах, если это не так.</span><span class="sxs-lookup"><span data-stu-id="f307c-128">The following example disables spin-waiting in critical sections when contended.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <Crst_DisableSpinWait enabled="1"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f307c-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f307c-129">See also</span></span>

- [<span data-ttu-id="f307c-130">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="f307c-130">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f307c-131">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="f307c-131">Configuration File Schema</span></span>](../index.md)

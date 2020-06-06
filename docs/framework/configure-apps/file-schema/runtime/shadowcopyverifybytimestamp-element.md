---
title: Элемент <shadowCopyVerifyByTimestamp>
ms.date: 03/30/2017
helpviewer_keywords:
- <shadowCopyTimeStampVerification> element
- shadowCopyTimeStampVerification element
ms.assetid: 2f1648e5-997b-435e-a4f9-d236c574c66c
ms.openlocfilehash: 160f14c856735e1ceac8635506aea52454faea43
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "73115729"
---
# <a name="shadowcopyverifybytimestamp-element"></a><span data-ttu-id="44fde-102">Элемент \<shadowCopyVerifyByTimestamp></span><span class="sxs-lookup"><span data-stu-id="44fde-102">\<shadowCopyVerifyByTimestamp> Element</span></span>
<span data-ttu-id="44fde-103">Указывает, использует ли теневое копирование поведение при запуске по умолчанию, представленное в .NET Framework 4, или возвращается к поведению при запуске более ранних версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44fde-103">Specifies whether shadow copying uses the default startup behavior introduced in the .NET Framework 4, or reverts to the startup behavior of earlier versions of the .NET Framework.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<shadowCopyVerifyByTimestamp>**  
  
## <a name="syntax"></a><span data-ttu-id="44fde-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="44fde-104">Syntax</span></span>  
  
```xml  
<shadowCopyVerifyByTimestamp enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44fde-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="44fde-105">Attributes and Elements</span></span>  
 <span data-ttu-id="44fde-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="44fde-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44fde-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="44fde-107">Attributes</span></span>  
  
|<span data-ttu-id="44fde-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="44fde-108">Attribute</span></span>|<span data-ttu-id="44fde-109">Описание:</span><span class="sxs-lookup"><span data-stu-id="44fde-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44fde-110">Включено</span><span class="sxs-lookup"><span data-stu-id="44fde-110">enabled</span></span>|<span data-ttu-id="44fde-111">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="44fde-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="44fde-112">Указывает, были ли домены приложений, использующие теневое копирование, сравниваются метки времени сборки при запуске, чтобы определить, обновлена ли сборка перед теневым копированием сборки.</span><span class="sxs-lookup"><span data-stu-id="44fde-112">Specifies whether application domains that use shadow copying compare assembly time stamps when starting up, to determine whether an assembly has been updated before shadow copying the assembly.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="44fde-113">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="44fde-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="44fde-114">Значение</span><span class="sxs-lookup"><span data-stu-id="44fde-114">Value</span></span>|<span data-ttu-id="44fde-115">Описание</span><span class="sxs-lookup"><span data-stu-id="44fde-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="44fde-116">Да</span><span class="sxs-lookup"><span data-stu-id="44fde-116">true</span></span>|<span data-ttu-id="44fde-117">При запуске копирует только сборки, которые были обновлены с момента последнего копирования в каталог теневых копий.</span><span class="sxs-lookup"><span data-stu-id="44fde-117">At startup, copies only assemblies that have been updated since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="44fde-118">Это значение по умолчанию для .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="44fde-118">This is the default for the .NET Framework 4.</span></span>|  
|<span data-ttu-id="44fde-119">false</span><span class="sxs-lookup"><span data-stu-id="44fde-119">false</span></span>|<span data-ttu-id="44fde-120">Восстанавливает поведение при запуске предыдущих версий .NET Framework, при запуске которого были скопированы все файлы.</span><span class="sxs-lookup"><span data-stu-id="44fde-120">Reverts to the startup behavior of previous versions of the .NET Framework, which was to copy all files at startup.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44fde-121">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="44fde-121">Child Elements</span></span>  
 <span data-ttu-id="44fde-122">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="44fde-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44fde-123">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="44fde-123">Parent Elements</span></span>  
  
|<span data-ttu-id="44fde-124">Элемент</span><span class="sxs-lookup"><span data-stu-id="44fde-124">Element</span></span>|<span data-ttu-id="44fde-125">Описание</span><span class="sxs-lookup"><span data-stu-id="44fde-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="44fde-126">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44fde-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="44fde-127">Содержит сведения о привязке сборок и сборке мусора.</span><span class="sxs-lookup"><span data-stu-id="44fde-127">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44fde-128">Примечания</span><span class="sxs-lookup"><span data-stu-id="44fde-128">Remarks</span></span>  
 <span data-ttu-id="44fde-129">Начиная с .NET Framework 4 сборки копируются только в том случае, если их метки времени указывают, что они изменились с момента последнего копирования в каталог теневых копий.</span><span class="sxs-lookup"><span data-stu-id="44fde-129">Starting with the .NET Framework 4, assemblies are shadow copied only if their time stamps indicate that they have changed since they were last copied to the shadow copy directory.</span></span> <span data-ttu-id="44fde-130">Это улучшает время запуска для многих приложений, использующих теневое копирование, как описано в разделе [теневое копирование сборок](../../../app-domains/shadow-copy-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="44fde-130">This improves startup times for many applications that use shadow copying, as described in [Shadow Copying Assemblies](../../../app-domains/shadow-copy-assemblies.md).</span></span> <span data-ttu-id="44fde-131">Для приложений с большим процентом и высокой частотой обновления сборок это изменение в поведении может не быть выгодно.</span><span class="sxs-lookup"><span data-stu-id="44fde-131">Applications that have a high percentage and frequency of assembly updates might not benefit from this change in behavior.</span></span> <span data-ttu-id="44fde-132">В этом случае можно использовать этот элемент для восстановления поведения предыдущих версий платформы .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44fde-132">In that case, you can use this element to restore the behavior of previous versions of the .NET Framework.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44fde-133">Пример</span><span class="sxs-lookup"><span data-stu-id="44fde-133">Example</span></span>  
 <span data-ttu-id="44fde-134">В следующем примере показано, как отключить поведение при запуске теневого копирования по умолчанию в .NET Framework 4 и вернуться к режиму запуска предыдущих версий .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="44fde-134">The following example shows how to disable the default startup behavior of shadow copying in the .NET Framework 4, and revert to the startup behavior of previous versions of the .NET Framework.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <shadowCopyVerifyByTimestamp enabled="false" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44fde-135">См. также</span><span class="sxs-lookup"><span data-stu-id="44fde-135">See also</span></span>

- [<span data-ttu-id="44fde-136">Схема параметров среды выполнения</span><span class="sxs-lookup"><span data-stu-id="44fde-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="44fde-137">Схема файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="44fde-137">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="44fde-138">Теневое копирование сборок</span><span class="sxs-lookup"><span data-stu-id="44fde-138">Shadow Copying Assemblies</span></span>](../../../app-domains/shadow-copy-assemblies.md)

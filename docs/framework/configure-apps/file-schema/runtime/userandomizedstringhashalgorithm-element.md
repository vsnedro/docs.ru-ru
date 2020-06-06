---
title: Элемент <UseRandomizedStringHashAlgorithm>
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UseRandomizedStringHashAlgorithm element
- <UseRandomizedStringHashAlgorithm> element
ms.assetid: c08125d6-56cc-4b23-b482-813ff85dc630
ms.openlocfilehash: a9afa0db516a542b74d08a4c3754a3244abbbea7
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153781"
---
# <a name="userandomizedstringhashalgorithm-element"></a><span data-ttu-id="67834-102">Элемент \<UseRandomizedStringHashAlgorithm></span><span class="sxs-lookup"><span data-stu-id="67834-102">\<UseRandomizedStringHashAlgorithm> Element</span></span>
<span data-ttu-id="67834-103">Определяет, вычисляет ли среда CLR хэш-коды для строк на уровне домена приложения.</span><span class="sxs-lookup"><span data-stu-id="67834-103">Determines whether the common language runtime calculates hash codes for strings on a per application domain basis.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<UseRandomizedStringHashAlgorithm>**  
  
## <a name="syntax"></a><span data-ttu-id="67834-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="67834-104">Syntax</span></span>  
  
```xml  
<UseRandomizedStringHashAlgorithm
   enabled=0|1 />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="67834-105">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="67834-105">Attributes and Elements</span></span>  
 <span data-ttu-id="67834-106">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="67834-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="67834-107">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="67834-107">Attributes</span></span>  
  
|<span data-ttu-id="67834-108">Атрибут</span><span class="sxs-lookup"><span data-stu-id="67834-108">Attribute</span></span>|<span data-ttu-id="67834-109">Описание</span><span class="sxs-lookup"><span data-stu-id="67834-109">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="67834-110">Обязательный атрибут.</span><span class="sxs-lookup"><span data-stu-id="67834-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="67834-111">Указывает, рассчитываются ли хэш-коды для строк на уровне домена приложения.</span><span class="sxs-lookup"><span data-stu-id="67834-111">Specifies whether hash codes for strings are calculated on a per application domain basis.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="67834-112">Атрибут enabled</span><span class="sxs-lookup"><span data-stu-id="67834-112">enabled Attribute</span></span>  
  
|<span data-ttu-id="67834-113">Значение</span><span class="sxs-lookup"><span data-stu-id="67834-113">Value</span></span>|<span data-ttu-id="67834-114">Описание</span><span class="sxs-lookup"><span data-stu-id="67834-114">Description</span></span>|  
|-----------|-----------------|  
|`0`|<span data-ttu-id="67834-115">Среда CLR не выполняет вычисление хэш-кодов для строк на уровне отдельных приложений. для вычисления хэш-кодов строк используется один алгоритм.</span><span class="sxs-lookup"><span data-stu-id="67834-115">The common language runtime does not compute hash codes for strings on a per application domain basis; a single algorithm is used to calculate string hash codes.</span></span> <span data-ttu-id="67834-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="67834-116">This is the default.</span></span>|  
|`1`|<span data-ttu-id="67834-117">Среда CLR выдает хэш-коды для строк на уровне домена приложения.</span><span class="sxs-lookup"><span data-stu-id="67834-117">The common language runtime computes hash codes for strings on a per application domain basis.</span></span> <span data-ttu-id="67834-118">Идентичные строки в разных доменах приложений и в разных процессах будут иметь разные хэш-коды.</span><span class="sxs-lookup"><span data-stu-id="67834-118">Identical strings in different application domains and in different processes will have different hash codes.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="67834-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="67834-119">Child Elements</span></span>  
 <span data-ttu-id="67834-120">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="67834-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="67834-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="67834-121">Parent Elements</span></span>  
  
|<span data-ttu-id="67834-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="67834-122">Element</span></span>|<span data-ttu-id="67834-123">Описание</span><span class="sxs-lookup"><span data-stu-id="67834-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="67834-124">Корневой элемент в любом файле конфигурации, используемом средой CLR и приложениями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="67834-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="67834-125">Содержит сведения о параметрах инициализации среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="67834-125">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67834-126">Примечания</span><span class="sxs-lookup"><span data-stu-id="67834-126">Remarks</span></span>  
 <span data-ttu-id="67834-127">По умолчанию <xref:System.StringComparer> класс и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод используют один алгоритм хэширования, который создает согласованный хэш-код между доменами приложений.</span><span class="sxs-lookup"><span data-stu-id="67834-127">By default, the <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method use a single hashing algorithm that produces a consistent hash code across application domains.</span></span> <span data-ttu-id="67834-128">Это эквивалентно присвоению `enabled` атрибуту элемента значения `<UseRandomizedStringHashAlgorithm>` `0` .</span><span class="sxs-lookup"><span data-stu-id="67834-128">This is equivalent to setting the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `0`.</span></span> <span data-ttu-id="67834-129">Это алгоритм хэширования, используемый в .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="67834-129">This is the hashing algorithm used in the .NET Framework 4.</span></span>  
  
 <span data-ttu-id="67834-130"><xref:System.StringComparer>Класс и <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> метод могут также использовать другой алгоритм хэширования, который выполняет вычисление хэш-кодов для каждого домена приложения.</span><span class="sxs-lookup"><span data-stu-id="67834-130">The <xref:System.StringComparer> class and the <xref:System.String.GetHashCode%2A?displayProperty=nameWithType> method can also use a different hashing algorithm that computes hash codes on a per application domain basis.</span></span> <span data-ttu-id="67834-131">В результате хэш-коды для эквивалентных строк будут различаться в разных доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="67834-131">As a result, hash codes for equivalent strings will differ across application domains.</span></span> <span data-ttu-id="67834-132">Эта функция является обязательной. чтобы воспользоваться его преимуществами, необходимо задать `enabled` атрибуту `<UseRandomizedStringHashAlgorithm>` элемента значение `1` .</span><span class="sxs-lookup"><span data-stu-id="67834-132">This is an opt-in feature; to take advantage of it, you must set the `enabled` attribute of the `<UseRandomizedStringHashAlgorithm>` element to `1`.</span></span>  
  
 <span data-ttu-id="67834-133">Поиск строки в хэш-таблице обычно является операцией O (1).</span><span class="sxs-lookup"><span data-stu-id="67834-133">The string lookup in a hash table is typically an O(1) operation.</span></span> <span data-ttu-id="67834-134">Однако при возникновении большого количества конфликтов Поиск может стать операцией O (n<sup>2</sup>).</span><span class="sxs-lookup"><span data-stu-id="67834-134">However, when a large number of collisions occur, the lookup can become an O(n<sup>2</sup>) operation.</span></span> <span data-ttu-id="67834-135">Элемент Configuration можно использовать `<UseRandomizedStringHashAlgorithm>` для создания случайного алгоритма хэширования на каждый домен приложения, который, в свою очередь, ограничивает количество потенциальных конфликтов, особенно когда ключи, из которых рассчитываются хэш-коды, основываются на вводе данных пользователями.</span><span class="sxs-lookup"><span data-stu-id="67834-135">You can use the `<UseRandomizedStringHashAlgorithm>` configuration element to generate a random hashing algorithm per application domain, which in turn limits the number of potential collisions, particularly when the keys from which the hash codes are calculated are based on data input by users.</span></span>  
  
## <a name="example"></a><span data-ttu-id="67834-136">Пример</span><span class="sxs-lookup"><span data-stu-id="67834-136">Example</span></span>  
 <span data-ttu-id="67834-137">В следующем примере определяется `DisplayString` класс, включающий закрытую строковую константу, `s` значение которой равно «это строка».</span><span class="sxs-lookup"><span data-stu-id="67834-137">The following example defines a `DisplayString` class that includes a private string constant, `s`, whose value is "This is a string."</span></span> <span data-ttu-id="67834-138">Он также включает метод `ShowStringHashCode`, который отображает значение строки и ее хэш-код вместе с именем домена приложения, в котором метод выполняется.</span><span class="sxs-lookup"><span data-stu-id="67834-138">It also includes a `ShowStringHashCode` method that displays the string value and its hash code along with the name of the application domain in which the method is executing.</span></span>  
  
 [!code-csharp[System.String.GetHashCode#2](../../../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.String.GetHashCode/CS/perdomain.cs#2)]
 [!code-vb[System.String.GetHashCode#2](../../../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.String.GetHashCode/VB/perdomain.vb#2)]  
  
 <span data-ttu-id="67834-139">При выполнении примера без указания файла конфигурации он отображает подобный следующему вывод.</span><span class="sxs-lookup"><span data-stu-id="67834-139">When you run the example without supplying a configuration file, it displays output similar to the following.</span></span> <span data-ttu-id="67834-140">Обратите внимание, что хэш-коды для строки идентичны в обоих доменах приложений.</span><span class="sxs-lookup"><span data-stu-id="67834-140">Note that the hash codes for the string are identical in the two application domains.</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 941BCEAC  
String 'This is a string.' in domain 'NewDomain': 941BCEAC  
```  
  
 <span data-ttu-id="67834-141">Однако при добавлении следующего файла конфигурации в каталог примеров и запуске примера, хэш-коды для той же строки будут отличаться по домену приложения.</span><span class="sxs-lookup"><span data-stu-id="67834-141">However, if you add the following configuration file to the example's directory and then run the example, the hash codes for the same string will differ by application domain.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
   <runtime>  
      <UseRandomizedStringHashAlgorithm enabled="1" />  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="67834-142">Если файл конфигурации существует, пример отображает следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="67834-142">When the configuration file is present, the example displays the following output:</span></span>  
  
```console
String 'This is a string.' in domain 'PerDomain.exe': 5435776D  
String 'This is a string.' in domain 'NewDomain': 75CC8236  
```  
  
## <a name="see-also"></a><span data-ttu-id="67834-143">См. также</span><span class="sxs-lookup"><span data-stu-id="67834-143">See also</span></span>

- <xref:System.StringComparer.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.String.GetHashCode%2A?displayProperty=nameWithType>
- <xref:System.Object.GetHashCode%2A?displayProperty=nameWithType>

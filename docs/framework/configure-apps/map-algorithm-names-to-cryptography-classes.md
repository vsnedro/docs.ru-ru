---
title: Отображение имен алгоритмов на криптографические классы
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 513000169504473aa6dd46feaca214f58502ffd0
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "69912866"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="e71c3-102">Отображение имен алгоритмов на криптографические классы</span><span class="sxs-lookup"><span data-stu-id="e71c3-102">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="e71c3-103">Существует четыре способа, с помощью которых разработчик может создать криптографический объект, используя Windows SDK:</span><span class="sxs-lookup"><span data-stu-id="e71c3-103">There are four ways a developer can create a cryptography object using the Windows SDK:</span></span>  
  
- <span data-ttu-id="e71c3-104">Создайте объект с помощью оператора **New** .</span><span class="sxs-lookup"><span data-stu-id="e71c3-104">Create an object by using the **new** operator.</span></span>  
  
- <span data-ttu-id="e71c3-105">Создайте объект, реализующий определенный алгоритм шифрования, вызвав метод **CREATE** для абстрактного класса для этого алгоритма.</span><span class="sxs-lookup"><span data-stu-id="e71c3-105">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
- <span data-ttu-id="e71c3-106">Создайте объект, реализующий определенный алгоритм шифрования, вызвав <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="e71c3-106">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="e71c3-107">Создайте объект, реализующий класс криптографических алгоритмов (например, симметричный блочный шифр), вызвав метод **CREATE** абстрактного класса для этого типа алгоритма (например, <xref:System.Security.Cryptography.SymmetricAlgorithm> ).</span><span class="sxs-lookup"><span data-stu-id="e71c3-107">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="e71c3-108">Например, предположим, что разработчик хочет вычислить хэш SHA1 набора байтов.</span><span class="sxs-lookup"><span data-stu-id="e71c3-108">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="e71c3-109"><xref:System.Security.Cryptography>Пространство имен содержит две реализации алгоритма SHA1, одну исключительно управляемую реализацию и одну оболочку CryptoAPI.</span><span class="sxs-lookup"><span data-stu-id="e71c3-109">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="e71c3-110">Разработчик может выбрать создание экземпляра конкретной реализации SHA1 (например, <xref:System.Security.Cryptography.SHA1Managed> ), вызвав оператор **New** .</span><span class="sxs-lookup"><span data-stu-id="e71c3-110">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="e71c3-111">Однако если не имеет значения, какой класс загружает общеязыковая среда выполнения, пока класс реализует хэш-алгоритм SHA1, разработчик может создать объект, вызвав <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="e71c3-111">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="e71c3-112">Этот метод вызывает **System. Security. Cryptography. CryptoConfig. CreateFromName («System. Security. Cryptography. SHA1»)**, который должен возвращать реализацию алгоритма хэширования SHA1.</span><span class="sxs-lookup"><span data-stu-id="e71c3-112">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="e71c3-113">Разработчик также может вызвать **System. Security. Cryptography. CryptoConfig. CreateFromName ("SHA1")** , так как по умолчанию конфигурация криптографии включает короткие имена для алгоритмов, поставляемых в .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e71c3-113">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="e71c3-114">Если не имеет значения, какой алгоритм хэширования используется, разработчик может вызвать <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> метод, который возвращает объект, реализующий преобразование хэширования.</span><span class="sxs-lookup"><span data-stu-id="e71c3-114">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="e71c3-115">Сопоставление имен алгоритмов в файлах конфигурации</span><span class="sxs-lookup"><span data-stu-id="e71c3-115">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="e71c3-116">По умолчанию среда выполнения возвращает <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> объект для всех четырех сценариев.</span><span class="sxs-lookup"><span data-stu-id="e71c3-116">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="e71c3-117">Однако администратор компьютера может изменить тип объекта, возвращаемый методами в двух последних сценариях.</span><span class="sxs-lookup"><span data-stu-id="e71c3-117">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="e71c3-118">Для этого необходимо связать понятное имя алгоритма с классом, который вы хотите использовать в файле конфигурации компьютера (Machine. config).</span><span class="sxs-lookup"><span data-stu-id="e71c3-118">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="e71c3-119">В следующем примере показано, как настроить среду выполнения таким образом, чтобы **система System. Security. Cryptography. SHA1. Create**, **System. Security. CryptoConfig. CREATEFROMNAME ("SHA1")** и **System. Security. Cryptography. HashAlgorithm. Create** возвращали `MySHA1HashClass` объект.</span><span class="sxs-lookup"><span data-stu-id="e71c3-119">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
```xml  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="e71c3-120">Имя атрибута можно указать в [ \> элементе<cryptoClass](./file-schema/cryptography/cryptoclass-element.md) (в предыдущем примере имя атрибута `MySHA1Hash` ).</span><span class="sxs-lookup"><span data-stu-id="e71c3-120">You can specify the name of the attribute in the [<cryptoClass\> element](./file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="e71c3-121">Значением атрибута в **\<cryptoClass>** элементе является строка, которую среда CLR использует для поиска класса.</span><span class="sxs-lookup"><span data-stu-id="e71c3-121">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="e71c3-122">Можно использовать любую строку, которая соответствует требованиям, указанным в указании [полных имен типов](../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="e71c3-122">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="e71c3-123">Многие имена алгоритмов могут сопоставляться с одним и тем же классом.</span><span class="sxs-lookup"><span data-stu-id="e71c3-123">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="e71c3-124">[ \<nameEntry> Элемент](./file-schema/cryptography/nameentry-element.md) сопоставляет класс с одним понятным именем алгоритма.</span><span class="sxs-lookup"><span data-stu-id="e71c3-124">The [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="e71c3-125">Атрибут **Name** может быть либо строкой, используемой при вызове метода **System. Security. Cryptography. CryptoConfig. CreateFromName** , либо именем абстрактного криптографического класса в <xref:System.Security.Cryptography> пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="e71c3-125">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="e71c3-126">Значением атрибута **Class** является имя атрибута в **\<cryptoClass>** элементе.</span><span class="sxs-lookup"><span data-stu-id="e71c3-126">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e71c3-127">Алгоритм SHA1 можно получить, вызвав <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> метод или **Security. CryptoConfig. CreateFromName ("SHA1")** .</span><span class="sxs-lookup"><span data-stu-id="e71c3-127">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="e71c3-128">Каждый метод гарантирует только то, что он возвращает объект, реализующий алгоритм SHA1.</span><span class="sxs-lookup"><span data-stu-id="e71c3-128">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="e71c3-129">Нет необходимости сопоставлять каждое понятное имя алгоритма с тем же классом в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="e71c3-129">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="e71c3-130">Список имен по умолчанию и классов, с которыми они сопоставляются, см. в разделе <xref:System.Security.Cryptography.CryptoConfig> .</span><span class="sxs-lookup"><span data-stu-id="e71c3-130">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e71c3-131">См. также</span><span class="sxs-lookup"><span data-stu-id="e71c3-131">See also</span></span>

- [<span data-ttu-id="e71c3-132">Службы шифрования</span><span class="sxs-lookup"><span data-stu-id="e71c3-132">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="e71c3-133">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="e71c3-133">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)

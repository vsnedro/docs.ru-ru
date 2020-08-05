---
title: Модель шифрования .NET
description: Ознакомьтесь с реализациями обычных криптографических алгоритмов в .NET. Изучение расширяемой криптографической модели наследования объектов, проектирования потоков & конфигурации.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], model
- encryption [.NET], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
ms.openlocfilehash: 0b3e07238bf0932572c222f7b947cfa7ae0221a9
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556999"
---
# <a name="net-cryptography-model"></a><span data-ttu-id="02448-104">Модель шифрования .NET</span><span class="sxs-lookup"><span data-stu-id="02448-104">.NET Cryptography Model</span></span>

<span data-ttu-id="02448-105">.NET предоставляет реализации многих стандартных криптографических алгоритмов, и модель шифрования .NET является расширяемой.</span><span class="sxs-lookup"><span data-stu-id="02448-105">.NET provides implementations of many standard cryptographic algorithms, and the .NET cryptography model is extensible.</span></span>

## <a name="object-inheritance"></a><span data-ttu-id="02448-106">Наследование объектов</span><span class="sxs-lookup"><span data-stu-id="02448-106">Object Inheritance</span></span>

<span data-ttu-id="02448-107">Система криптографии .NET реализует расширяемый шаблон наследования производного класса.</span><span class="sxs-lookup"><span data-stu-id="02448-107">The .NET cryptography system implements an extensible pattern of derived class inheritance.</span></span> <span data-ttu-id="02448-108">Иерархия имеет представленный ниже вид.</span><span class="sxs-lookup"><span data-stu-id="02448-108">The hierarchy is as follows:</span></span>

- <span data-ttu-id="02448-109">Класс типа алгоритма, например <xref:System.Security.Cryptography.SymmetricAlgorithm> , <xref:System.Security.Cryptography.AsymmetricAlgorithm> или <xref:System.Security.Cryptography.HashAlgorithm> .</span><span class="sxs-lookup"><span data-stu-id="02448-109">Algorithm type class, such as <xref:System.Security.Cryptography.SymmetricAlgorithm>,  <xref:System.Security.Cryptography.AsymmetricAlgorithm>, or <xref:System.Security.Cryptography.HashAlgorithm>.</span></span> <span data-ttu-id="02448-110">Этот уровень является абстрактным.</span><span class="sxs-lookup"><span data-stu-id="02448-110">This level is abstract.</span></span>

- <span data-ttu-id="02448-111">Класс алгоритма, наследующий от класса типа алгоритма, например <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RSA> или <xref:System.Security.Cryptography.ECDiffieHellman>.</span><span class="sxs-lookup"><span data-stu-id="02448-111">Algorithm class that inherits from an algorithm type class; for example, <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RSA>, or <xref:System.Security.Cryptography.ECDiffieHellman>.</span></span> <span data-ttu-id="02448-112">Этот уровень является абстрактным.</span><span class="sxs-lookup"><span data-stu-id="02448-112">This level is abstract.</span></span>

- <span data-ttu-id="02448-113">Реализация класса алгоритма, наследующего от класса алгоритма, например <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider> или <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span><span class="sxs-lookup"><span data-stu-id="02448-113">Implementation of an algorithm class that inherits from an algorithm class; for example, <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider>, or <xref:System.Security.Cryptography.ECDiffieHellmanCng>.</span></span> <span data-ttu-id="02448-114">Этот уровень полностью реализован.</span><span class="sxs-lookup"><span data-stu-id="02448-114">This level is fully implemented.</span></span>

<span data-ttu-id="02448-115">Этот шаблон производных классов позволяет добавить новый алгоритм или новую реализацию существующего алгоритма.</span><span class="sxs-lookup"><span data-stu-id="02448-115">This pattern of derived classes lets you add a new algorithm or a new implementation of an existing algorithm.</span></span> <span data-ttu-id="02448-116">Например, чтобы создать новый алгоритм открытого ключа, можно наследовать от класса <xref:System.Security.Cryptography.AsymmetricAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="02448-116">For example, to create a new public-key algorithm, you would inherit from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class.</span></span> <span data-ttu-id="02448-117">Чтобы создать новую реализацию определенного алгоритма, можно создать неабстрактный производный класс этого алгоритма.</span><span class="sxs-lookup"><span data-stu-id="02448-117">To create a new implementation of a specific algorithm, you would create a non-abstract derived class of that algorithm.</span></span>

## <a name="how-algorithms-are-implemented-in-net"></a><span data-ttu-id="02448-118">Реализация алгоритмов в .NET</span><span class="sxs-lookup"><span data-stu-id="02448-118">How Algorithms Are Implemented in .NET</span></span>

<span data-ttu-id="02448-119">В качестве примера различных реализаций, доступных для алгоритма, рассмотрим симметричные алгоритмы.</span><span class="sxs-lookup"><span data-stu-id="02448-119">As an example of the different implementations available for an algorithm, consider symmetric algorithms.</span></span> <span data-ttu-id="02448-120">Основой для всех симметричных алгоритмов является <xref:System.Security.Cryptography.SymmetricAlgorithm> , которая наследуется <xref:System.Security.Cryptography.Aes> , <xref:System.Security.Cryptography.TripleDES> и другие, которые больше не рекомендуются.</span><span class="sxs-lookup"><span data-stu-id="02448-120">The base for all symmetric algorithms is <xref:System.Security.Cryptography.SymmetricAlgorithm>, which is inherited by <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.TripleDES>, and others that are no longer recommended.</span></span>

<span data-ttu-id="02448-121"><xref:System.Security.Cryptography.Aes>наследуется <xref:System.Security.Cryptography.AesCryptoServiceProvider> , <xref:System.Security.Cryptography.AesCng> и <xref:System.Security.Cryptography.AesManaged> .</span><span class="sxs-lookup"><span data-stu-id="02448-121"><xref:System.Security.Cryptography.Aes> is inherited by <xref:System.Security.Cryptography.AesCryptoServiceProvider>, <xref:System.Security.Cryptography.AesCng>, and <xref:System.Security.Cryptography.AesManaged>.</span></span>

<span data-ttu-id="02448-122">В .NET Framework в Windows:</span><span class="sxs-lookup"><span data-stu-id="02448-122">In .NET Framework on Windows:</span></span>

* <span data-ttu-id="02448-123">`*CryptoServiceProvider`классы алгоритмов, такие как <xref:System.Security.Cryptography.AesCryptoServiceProvider> , являются оболочками для реализации алгоритма с помощью API шифрования Windows (CAPI).</span><span class="sxs-lookup"><span data-stu-id="02448-123">`*CryptoServiceProvider` algorithm classes, such as <xref:System.Security.Cryptography.AesCryptoServiceProvider>, are wrappers around the Windows Cryptography API (CAPI) implementation of an algorithm.</span></span>
* <span data-ttu-id="02448-124">`*Cng`классы алгоритмов, такие как, <xref:System.Security.Cryptography.ECDiffieHellmanCng> являются оболочками для реализации Windows криптографии следующего поколения (CNG).</span><span class="sxs-lookup"><span data-stu-id="02448-124">`*Cng` algorithm classes, such as <xref:System.Security.Cryptography.ECDiffieHellmanCng> are wrappers around the Windows Cryptography Next Generation (CNG) implementation.</span></span>
* <span data-ttu-id="02448-125">`*Managed`классы, такие как <xref:System.Security.Cryptography.AesManaged> , полностью записываются в управляемом коде.</span><span class="sxs-lookup"><span data-stu-id="02448-125">`*Managed` classes, such as <xref:System.Security.Cryptography.AesManaged>, are written entirely in managed code.</span></span> <span data-ttu-id="02448-126">`*Managed`реализации не сертифицированы Федеральным стандартом обработки информации (FIPS) и могут быть медленнее, чем `*CryptoServiceProvider` классы- `*Cng` оболочки.</span><span class="sxs-lookup"><span data-stu-id="02448-126">`*Managed` implementations are not certified by the Federal Information Processing Standards (FIPS), and may be slower than the `*CryptoServiceProvider` and `*Cng` wrapper classes.</span></span>

<span data-ttu-id="02448-127">В .NET Core и .NET 5 и более поздних версиях все классы реализации ( `*CryptoServiceProvider` , `*Managed` и `*Cng` ) являются оболочками для алгоритмов операционной системы (ОС).</span><span class="sxs-lookup"><span data-stu-id="02448-127">In .NET Core and .NET 5 and later versions, all implementation classes (`*CryptoServiceProvider`, `*Managed`, and `*Cng`) are wrappers for the operating system (OS) algorithms.</span></span> <span data-ttu-id="02448-128">Если алгоритмы ОС сертифицированы по стандарту FIPS, .NET использует алгоритмы, сертифицированные FIPS.</span><span class="sxs-lookup"><span data-stu-id="02448-128">If the OS algorithms are FIPS-certified, then .NET uses FIPS-certified algorithms.</span></span> <span data-ttu-id="02448-129">Дополнительные сведения см. в статье [кросс-платформенное шифрование](cross-platform-cryptography.md).</span><span class="sxs-lookup"><span data-stu-id="02448-129">For more information, see [Cross-Platform Cryptography](cross-platform-cryptography.md).</span></span>

<span data-ttu-id="02448-130">В большинстве случаев нет необходимости напрямую ссылаться на класс реализации алгоритма, например `AesCryptoServiceProvider` .</span><span class="sxs-lookup"><span data-stu-id="02448-130">In most cases, you don't need to directly reference an algorithm implementation class, such as `AesCryptoServiceProvider`.</span></span> <span data-ttu-id="02448-131">Обычно нужные методы и свойства находятся в классе базового алгоритма, например `Aes` .</span><span class="sxs-lookup"><span data-stu-id="02448-131">The methods and properties you typically need are on the base algorithm class, such as `Aes`.</span></span> <span data-ttu-id="02448-132">Создайте экземпляр класса реализации по умолчанию, используя фабричный метод в классе базового алгоритма и обратитесь к классу базового алгоритма.</span><span class="sxs-lookup"><span data-stu-id="02448-132">Create an instance of a default implementation class by using a factory method on the base algorithm class, and refer to the base algorithm class.</span></span> <span data-ttu-id="02448-133">Например, см. выделенную строку кода в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="02448-133">For example, see the highlighted line of code in the following example:</span></span>

:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs" highlight="16":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb" highlight="12":::

## <a name="cryptographic-configuration"></a><span data-ttu-id="02448-134">Криптографическая конфигурация</span><span class="sxs-lookup"><span data-stu-id="02448-134">Cryptographic Configuration</span></span>

<span data-ttu-id="02448-135">Конфигурация криптографии позволяет разрешать определенную реализацию алгоритма в имя алгоритма, обеспечивая расширяемость классов шифрования .NET.</span><span class="sxs-lookup"><span data-stu-id="02448-135">Cryptographic configuration lets you resolve a specific implementation of an algorithm to an algorithm name, allowing extensibility of the .NET cryptography classes.</span></span> <span data-ttu-id="02448-136">Вы можете добавить свою собственную аппаратную или программную реализацию алгоритма и сопоставить ее с необходимым именем алгоритма.</span><span class="sxs-lookup"><span data-stu-id="02448-136">You can add your own hardware or software implementation of an algorithm and map the implementation to the algorithm name of your choice.</span></span> <span data-ttu-id="02448-137">Если алгоритм не задан в файле конфигурации, используются параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="02448-137">If an algorithm is not specified in the configuration file, the default settings are used.</span></span>

## <a name="choosing-an-algorithm"></a><span data-ttu-id="02448-138">Выбор алгоритма</span><span class="sxs-lookup"><span data-stu-id="02448-138">Choosing an Algorithm</span></span>

<span data-ttu-id="02448-139">Алгоритм можно выбирать, исходя из различных причин, например для обеспечения целостности данных, для обеспечения конфиденциальности данных или для создания ключа.</span><span class="sxs-lookup"><span data-stu-id="02448-139">You can select an algorithm for different reasons: for example, for data integrity, for data privacy, or to generate a key.</span></span> <span data-ttu-id="02448-140">Симметричные и хэш-алгоритмы предназначены для защиты данных от нарушения целостности (защита от изменения) или конфиденциальности (защита от просмотра).</span><span class="sxs-lookup"><span data-stu-id="02448-140">Symmetric and hash algorithms are intended for protecting data for either integrity reasons (protect from change) or privacy reasons (protect from viewing).</span></span> <span data-ttu-id="02448-141">Хэш-алгоритмы используются в основном для обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="02448-141">Hash algorithms are used primarily for data integrity.</span></span>

<span data-ttu-id="02448-142">Ниже приведен список рекомендуемых алгоритмов в зависимости от приложения.</span><span class="sxs-lookup"><span data-stu-id="02448-142">Here is a list of recommended algorithms by application:</span></span>

- <span data-ttu-id="02448-143">Конфиденциальность данных:</span><span class="sxs-lookup"><span data-stu-id="02448-143">Data privacy:</span></span>
  - <xref:System.Security.Cryptography.Aes>
- <span data-ttu-id="02448-144">Целостность данных:</span><span class="sxs-lookup"><span data-stu-id="02448-144">Data integrity:</span></span>
  - <xref:System.Security.Cryptography.HMACSHA256>
  - <xref:System.Security.Cryptography.HMACSHA512>
- <span data-ttu-id="02448-145">Цифровая подпись:</span><span class="sxs-lookup"><span data-stu-id="02448-145">Digital signature:</span></span>
  - <xref:System.Security.Cryptography.ECDsa>
  - <xref:System.Security.Cryptography.RSA>
- <span data-ttu-id="02448-146">Обмен ключами:</span><span class="sxs-lookup"><span data-stu-id="02448-146">Key exchange:</span></span>
  - <xref:System.Security.Cryptography.ECDiffieHellman>
  - <xref:System.Security.Cryptography.RSA>
- <span data-ttu-id="02448-147">Генерация случайных чисел:</span><span class="sxs-lookup"><span data-stu-id="02448-147">Random number generation:</span></span>
  - <xref:System.Security.Cryptography.RandomNumberGenerator.Create%2A?displayProperty=nameWithType>
- <span data-ttu-id="02448-148">Формирование ключа из пароля:</span><span class="sxs-lookup"><span data-stu-id="02448-148">Generating a key from a password:</span></span>
  - <xref:System.Security.Cryptography.Rfc2898DeriveBytes>

## <a name="see-also"></a><span data-ttu-id="02448-149">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="02448-149">See also</span></span>

- [<span data-ttu-id="02448-150">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="02448-150">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="02448-151">Кросс-платформенная криптография</span><span class="sxs-lookup"><span data-stu-id="02448-151">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="02448-152">ASP.NET Core Защита данных</span><span class="sxs-lookup"><span data-stu-id="02448-152">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)

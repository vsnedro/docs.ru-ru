---
title: Создание ключей для шифрования и расшифровки
description: Узнайте, как создавать симметричные и асимметричные ключи для шифрования и расшифровки в .NET и управлять ими.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET], keys
- symmetric keys
- asymmetric keys [.NET]
- cryptography [.NET], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
ms.openlocfilehash: 2af54cef4f233b7bcae5c476f1aa49fdbf7ef2fc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689723"
---
# <a name="generating-keys-for-encryption-and-decryption"></a><span data-ttu-id="87e7a-103">Создание ключей для шифрования и расшифровки</span><span class="sxs-lookup"><span data-stu-id="87e7a-103">Generating Keys for Encryption and Decryption</span></span>

<span data-ttu-id="87e7a-104">Создание ключей и управление ими — это важная часть процесса шифрования.</span><span class="sxs-lookup"><span data-stu-id="87e7a-104">Creating and managing keys is an important part of the cryptographic process.</span></span> <span data-ttu-id="87e7a-105">Симметричные алгоритмы требуют создания ключа и вектора инициализации (IV).</span><span class="sxs-lookup"><span data-stu-id="87e7a-105">Symmetric algorithms require the creation of a key and an initialization vector (IV).</span></span> <span data-ttu-id="87e7a-106">Ключ следует хранить в тайне от любого, кто не должен расшифровывать ваши данные.</span><span class="sxs-lookup"><span data-stu-id="87e7a-106">The key must be kept secret from anyone who should not decrypt your data.</span></span> <span data-ttu-id="87e7a-107">Вектор инициализации может не быть секретным, но должен изменяться для каждого сеанса.</span><span class="sxs-lookup"><span data-stu-id="87e7a-107">The IV does not have to be secret, but should be changed for each session.</span></span> <span data-ttu-id="87e7a-108">Асимметричные алгоритмы требуют создания открытого ключа и закрытого ключа.</span><span class="sxs-lookup"><span data-stu-id="87e7a-108">Asymmetric algorithms require the creation of a public key and a private key.</span></span> <span data-ttu-id="87e7a-109">Открытый ключ можно предоставлять кому угодно, а закрытый ключ должен быть известен только той стороне, которая будет расшифровывать данные, зашифрованные при помощи открытого ключа.</span><span class="sxs-lookup"><span data-stu-id="87e7a-109">The public key can be made public to anyone, while the private key must known only by the party who will decrypt the data encrypted with the public key.</span></span> <span data-ttu-id="87e7a-110">В этом разделе описывается создание ключей и управление ими для симметричных и асимметричных алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="87e7a-110">This section describes how to generate and manage keys for both symmetric and asymmetric algorithms.</span></span>  
  
## <a name="symmetric-keys"></a><span data-ttu-id="87e7a-111">симметричные ключи;</span><span class="sxs-lookup"><span data-stu-id="87e7a-111">Symmetric Keys</span></span>  

 <span data-ttu-id="87e7a-112">Классы симметричного шифрования, предоставляемые .NET, нуждаются в ключе и новом векторе инициализации (IV) для шифрования и расшифровки данных.</span><span class="sxs-lookup"><span data-stu-id="87e7a-112">The symmetric encryption classes supplied by .NET require a key and a new initialization vector (IV) to encrypt and decrypt data.</span></span> <span data-ttu-id="87e7a-113">При создании нового экземпляра одного из управляемых симметричных криптографических классов с помощью метода без параметров `Create()` автоматически создаются новый ключ и вектор инициализации.</span><span class="sxs-lookup"><span data-stu-id="87e7a-113">Whenever you create a new instance of one of the managed symmetric cryptographic classes using the parameterless `Create()` method, a new key and IV are automatically created.</span></span> <span data-ttu-id="87e7a-114">Все пользователи, которым вы разрешаете расшифровывать свои данные, должны иметь тот же ключ и вектора инициализации и использовать тот же алгоритм.</span><span class="sxs-lookup"><span data-stu-id="87e7a-114">Anyone that you allow to decrypt your data must possess the same key and IV and use the same algorithm.</span></span> <span data-ttu-id="87e7a-115">Как правило, новый ключ и вектор инициализации должны создаваться для каждого сеанса, и ни вектор инициализации, ни ключ нельзя сохранять для использования в следующем сеансе.</span><span class="sxs-lookup"><span data-stu-id="87e7a-115">Generally, a new key and IV should be created for every session, and neither the key nor IV should be stored for use in a later session.</span></span>  
  
 <span data-ttu-id="87e7a-116">При передаче симметричного ключа и вектора инициализации на удаленную сторону симметричный ключ обычно шифруется с помощью асимметричного шифрования.</span><span class="sxs-lookup"><span data-stu-id="87e7a-116">To communicate a symmetric key and IV to a remote party, you would usually encrypt the symmetric key by using asymmetric encryption.</span></span> <span data-ttu-id="87e7a-117">Отправка ключа через незащищенную сеть без шифрования небезопасна, так как любой, кто перехватит ключ и вектор инициализации, сможет расшифровать данные.</span><span class="sxs-lookup"><span data-stu-id="87e7a-117">Sending the key across an insecure network without encrypting it is unsafe, because anyone who intercepts the key and IV can then decrypt your data.</span></span>  
  
 <span data-ttu-id="87e7a-118">В следующем примере показано создание нового экземпляра класса реализации по умолчанию для <xref:System.Security.Cryptography.Aes> алгоритма.</span><span class="sxs-lookup"><span data-stu-id="87e7a-118">The following example shows the creation of a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span>  
  
```vb  
Dim aes As Aes = Aes.Create()  
```  
  
```csharp  
Aes aes = Aes.Create();  
```  
  
 <span data-ttu-id="87e7a-119">При выполнении предыдущего кода осуществляется создание нового ключа и вектора инициализации и их помещение в свойства **Key** и **IV** соответственно.</span><span class="sxs-lookup"><span data-stu-id="87e7a-119">When the previous code is executed, a new key and IV are generated and placed in the **Key** and **IV** properties, respectively.</span></span>  
  
 <span data-ttu-id="87e7a-120">Иногда может понадобиться создать несколько ключей.</span><span class="sxs-lookup"><span data-stu-id="87e7a-120">Sometimes you might need to generate multiple keys.</span></span> <span data-ttu-id="87e7a-121">В этом случае можно создать новый экземпляр класса, реализующий симметричный алгоритм, а затем создать новый ключ и вектор инициализации, вызвав методы **GenerateKey** и **GenerateIV** .</span><span class="sxs-lookup"><span data-stu-id="87e7a-121">In this situation, you can create a new instance of a class that implements a symmetric algorithm and then create a new key and IV by calling the **GenerateKey** and **GenerateIV** methods.</span></span> <span data-ttu-id="87e7a-122">В следующем примере кода показано, как создать новые ключи и IVs после внесения нового экземпляра симметричного криптографического класса.</span><span class="sxs-lookup"><span data-stu-id="87e7a-122">The following code example illustrates how to create new keys and IVs after a new instance of the symmetric cryptographic class has been made.</span></span>  
  
```vb  
Dim aes As Aes = Aes.Create()  
aes.GenerateIV()  
aes.GenerateKey()  
```  
  
```csharp  
Aes aes = Aes.Create();  
aes.GenerateIV();  
aes.GenerateKey();  
```  
  
 <span data-ttu-id="87e7a-123">При выполнении приведенного выше кода ключ и вектор инициализации создаются при создании нового экземпляра **AES** .</span><span class="sxs-lookup"><span data-stu-id="87e7a-123">When the preceding code is executed, a key and IV are generated when the new instance of **Aes** is made.</span></span> <span data-ttu-id="87e7a-124">Другой ключ и вектор инициализации создаются при вызове методов **GenerateKey** и **GenerateIV** .</span><span class="sxs-lookup"><span data-stu-id="87e7a-124">Another key and IV are created when the **GenerateKey** and **GenerateIV** methods are called.</span></span>
  
## <a name="asymmetric-keys"></a><span data-ttu-id="87e7a-125">Асимметричные ключи</span><span class="sxs-lookup"><span data-stu-id="87e7a-125">Asymmetric Keys</span></span>

 <span data-ttu-id="87e7a-126">.NET предоставляет <xref:System.Security.Cryptography.RSA> класс для асимметричного шифрования.</span><span class="sxs-lookup"><span data-stu-id="87e7a-126">.NET provides the <xref:System.Security.Cryptography.RSA> class for asymmetric encryption.</span></span> <span data-ttu-id="87e7a-127">Этот класс создает пару открытого и закрытого ключей при использовании метода без параметров `Create()` для создания нового экземпляра.</span><span class="sxs-lookup"><span data-stu-id="87e7a-127">This class creates a public/private key pair when you use the parameterless `Create()` method to create a new instance.</span></span> <span data-ttu-id="87e7a-128">Асимметричные ключи можно сохранять для использования в нескольких сеансах или создавать только для отдельного сеанса.</span><span class="sxs-lookup"><span data-stu-id="87e7a-128">Asymmetric keys can be either stored for use in multiple sessions or generated for one session only.</span></span> <span data-ttu-id="87e7a-129">В то время как открытый ключ можно сделать общедоступным, закрытый ключ должен быть надежно защищен.</span><span class="sxs-lookup"><span data-stu-id="87e7a-129">While the public key can be made generally available, the private key should be closely guarded.</span></span>  
  
 <span data-ttu-id="87e7a-130">Пара из открытого и закрытого ключей создается каждый раз, когда создается новый экземпляр класса асимметричного алгоритма.</span><span class="sxs-lookup"><span data-stu-id="87e7a-130">A public/private key pair is generated whenever a new instance of an asymmetric algorithm class is created.</span></span> <span data-ttu-id="87e7a-131">После создания нового экземпляра класса сведения о ключе можно извлечь с помощью <xref:System.Security.Cryptography.RSA.ExportParameters%2A> метода, который возвращает <xref:System.Security.Cryptography.RSAParameters> структуру, содержащую сведения о ключе.</span><span class="sxs-lookup"><span data-stu-id="87e7a-131">After a new instance of the class is created, the key information can be extracted using the <xref:System.Security.Cryptography.RSA.ExportParameters%2A> method, which returns an <xref:System.Security.Cryptography.RSAParameters> structure that holds the key information.</span></span> <span data-ttu-id="87e7a-132">Метод принимает логическое значение, указывающее, следует ли возвращать только сведения об открытом ключе или как сведения об открытом ключе, так и о закрытом ключе.</span><span class="sxs-lookup"><span data-stu-id="87e7a-132">The method accepts a Boolean value that indicates whether to return only the public key information or to return both the public-key and the private-key information.</span></span>

<span data-ttu-id="87e7a-133">Существуют также и другие методы, позволяющие извлекать ключевые сведения, например:</span><span class="sxs-lookup"><span data-stu-id="87e7a-133">There are also other methods that let you extract key information, such as:</span></span>

* <xref:System.Security.Cryptography.RSA.ExportRSAPublicKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.RSA.ExportRSAPrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportSubjectPublicKeyInfo%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportPkcs8PrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportEncryptedPkcs8PrivateKey%2A?displayProperty=nameWithType>

<span data-ttu-id="87e7a-134">Экземпляр **RSA** можно инициализировать со значением структуры **RSAParameters** с помощью <xref:System.Security.Cryptography.RSA.ImportParameters%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="87e7a-134">An **RSA** instance can be initialized to the value of an **RSAParameters** structure by using the <xref:System.Security.Cryptography.RSA.ImportParameters%2A> method.</span></span> <span data-ttu-id="87e7a-135">Или создайте новый экземпляр с помощью <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> метода.</span><span class="sxs-lookup"><span data-stu-id="87e7a-135">Or create a new instance by using the <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="87e7a-136">Асимметричные закрытые ключи никогда не следует хранить буквальной форме или в формате обычного текста на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="87e7a-136">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="87e7a-137">Если необходимо хранить закрытый ключ, следует использовать для этого контейнер ключа.</span><span class="sxs-lookup"><span data-stu-id="87e7a-137">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="87e7a-138">Дополнительные сведения о хранении закрытого ключа в контейнере ключей см. в разделе [как хранить асимметричные ключи в контейнере ключей](how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="87e7a-138">For more information about how to store a private key in a key container, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>  
  
 <span data-ttu-id="87e7a-139">В следующем примере кода создается новый экземпляр класса **RSA** , который создает пару из открытого и закрытого ключей и сохраняет сведения об открытом ключе в структуре **RSAParameters** .</span><span class="sxs-lookup"><span data-stu-id="87e7a-139">The following code example creates a new instance of the **RSA** class, creating a public/private key pair, and saves the public key information to an **RSAParameters** structure.</span></span>  
  
```vb  
'Generate a public/private key pair.  
Dim rsa as RSA = RSA.Create()  
'Save the public key information to an RSAParameters structure.  
Dim rsaKeyInfo As RSAParameters = rsa.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSA rsa = RSA.Create();  
//Save the public key information to an RSAParameters structure.  
RSAParameters rsaKeyInfo = rsa.ExportParameters(false);  
```  
  
## <a name="see-also"></a><span data-ttu-id="87e7a-140">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="87e7a-140">See also</span></span>

- [<span data-ttu-id="87e7a-141">Шифрование данных</span><span class="sxs-lookup"><span data-stu-id="87e7a-141">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="87e7a-142">Расшифровка данных</span><span class="sxs-lookup"><span data-stu-id="87e7a-142">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="87e7a-143">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="87e7a-143">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="87e7a-144">Практическое руководство. Хранение асимметричных ключей в контейнере ключей</span><span class="sxs-lookup"><span data-stu-id="87e7a-144">How to: Store Asymmetric Keys in a Key Container</span></span>](how-to-store-asymmetric-keys-in-a-key-container.md)
- [<span data-ttu-id="87e7a-145">Кросс-платформенная криптография</span><span class="sxs-lookup"><span data-stu-id="87e7a-145">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="87e7a-146">ASP.NET Core Защита данных</span><span class="sxs-lookup"><span data-stu-id="87e7a-146">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)

---
title: Криптографические подписи
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- digital signatures
- cryptography [.NET], signatures
- digital signatures, XML signing
- signatures, cryptographic
- digital signatures, generating
- verifying signatures
- generating signatures
- digital signatures, about
- encryption [.NET], signatures
- security [.NET], signatures
- XML signing
- digital signatures, verifying
- signing XML
ms.assetid: aa87cb7f-e608-4a81-948b-c9b8a1225783
ms.openlocfilehash: ce2be1d509da4e399bf87e1c8df7ba061fc2707c
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557012"
---
# <a name="cryptographic-signatures"></a><span data-ttu-id="ee48b-102">Криптографические подписи</span><span class="sxs-lookup"><span data-stu-id="ee48b-102">Cryptographic Signatures</span></span>

<span data-ttu-id="ee48b-103">Криптографические цифровые подписи используют алгоритмы с открытым ключом для обеспечения целостности данных.</span><span class="sxs-lookup"><span data-stu-id="ee48b-103">Cryptographic digital signatures use public key algorithms to provide data integrity.</span></span> <span data-ttu-id="ee48b-104">Если вы подписываете данные с помощью цифровой подписи, другая сторона может проверить подпись и убедиться в том, что данные поступили от вас и не были изменены после подписывания.</span><span class="sxs-lookup"><span data-stu-id="ee48b-104">When you sign data with a digital signature, someone else can verify the signature, and can prove that the data originated from you and was not altered after you signed it.</span></span> <span data-ttu-id="ee48b-105">Подробнее о цифровых подписях см. в разделе [Cryptographic Services](cryptographic-services.md).</span><span class="sxs-lookup"><span data-stu-id="ee48b-105">For more information about digital signatures, see [Cryptographic Services](cryptographic-services.md).</span></span>

<span data-ttu-id="ee48b-106">В этом разделе описывается создание и проверка цифровых подписей с помощью классов пространства имен <xref:System.Security.Cryptography> .</span><span class="sxs-lookup"><span data-stu-id="ee48b-106">This topic explains how to generate and verify digital signatures using classes in the <xref:System.Security.Cryptography> namespace.</span></span>

## <a name="generating-signatures"></a><span data-ttu-id="ee48b-107">Создание подписей</span><span class="sxs-lookup"><span data-stu-id="ee48b-107">Generating Signatures</span></span>

<span data-ttu-id="ee48b-108">Цифровые подписи обычно применяются к хэш-значениям, которые представляют массивы данных большого размера.</span><span class="sxs-lookup"><span data-stu-id="ee48b-108">Digital signatures are usually applied to hash values that represent larger data.</span></span> <span data-ttu-id="ee48b-109">В примере ниже демонстрируется применение цифровой подписи к хэш-значению.</span><span class="sxs-lookup"><span data-stu-id="ee48b-109">The following example applies a digital signature to a hash value.</span></span> <span data-ttu-id="ee48b-110">Сначала создается экземпляр класса <xref:System.Security.Cryptography.RSA> с целью формирования набора, состоящего из открытого и закрытого ключей.</span><span class="sxs-lookup"><span data-stu-id="ee48b-110">First, a new instance of the <xref:System.Security.Cryptography.RSA> class is created to generate a public/private key pair.</span></span> <span data-ttu-id="ee48b-111">Затем экземпляр <xref:System.Security.Cryptography.RSA> передается в новый экземпляр класса <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> .</span><span class="sxs-lookup"><span data-stu-id="ee48b-111">Next, the <xref:System.Security.Cryptography.RSA> is passed to a new instance of the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class.</span></span> <span data-ttu-id="ee48b-112">При этом экземпляру <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>передается закрытый ключ, который и создает цифровую подпись.</span><span class="sxs-lookup"><span data-stu-id="ee48b-112">This transfers the private key to the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, which actually performs the digital signing.</span></span> <span data-ttu-id="ee48b-113">Перед тем как подписать хэш-код, вам необходимо указать используемый хэш-алгоритм.</span><span class="sxs-lookup"><span data-stu-id="ee48b-113">Before you can sign the hash code, you must specify a hash algorithm to use.</span></span> <span data-ttu-id="ee48b-114">В этом примере используется алгоритм SHA1.</span><span class="sxs-lookup"><span data-stu-id="ee48b-114">This example uses the SHA1 algorithm.</span></span> <span data-ttu-id="ee48b-115">Наконец, вызывается метод <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> для выполнения подписи.</span><span class="sxs-lookup"><span data-stu-id="ee48b-115">Finally, the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> method is called to perform the signing.</span></span>

<span data-ttu-id="ee48b-116">Из-за проблем с алгоритмом SHA1 рекомендуется использовать SHA256 или более высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="ee48b-116">Due to collision problems with SHA1, we recommend SHA256 or better.</span></span>

```vb
Imports System.Security.Cryptography

Module Module1
    Sub Main()
        'The hash value to sign.
        Dim hashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}

        'The value to hold the signed value.
        Dim signedHashValue() As Byte

        'Generate a public/private key pair.
        Dim rsa As RSA = RSA.Create()

        'Create an RSAPKCS1SignatureFormatter object and pass it
        'the RSA instance to transfer the private key.
        Dim rsaFormatter As New RSAPKCS1SignatureFormatter(rsa)

        'Set the hash algorithm to SHA1.
        rsaFormatter.SetHashAlgorithm("SHA1")

        'Create a signature for hashValue and assign it to
        'signedHashValue.
        signedHashValue = rsaFormatter.CreateSignature(hashValue)
    End Sub
End Module
```

```csharp
using System;
using System.Security.Cryptography;

class Class1
{
   static void Main()
   {
      //The hash value to sign.
      byte[] hashValue = {59,4,248,102,77,97,142,201,210,12,224,93,25,41,100,197,213,134,130,135};

      //The value to hold the signed value.
      byte[] signedHashValue;

      //Generate a public/private key pair.
      RSA rsa = RSA.Create();

      //Create an RSAPKCS1SignatureFormatter object and pass it the
      //RSA instance to transfer the private key.
      RSAPKCS1SignatureFormatter rsaFormatter = new RSAPKCS1SignatureFormatter(rsa);

      //Set the hash algorithm to SHA1.
      rsaFormatter.SetHashAlgorithm("SHA1");

      //Create a signature for hashValue and assign it to
      //signedHashValue.
      signedHashValue = rsaFormatter.CreateSignature(hashValue);
   }
}
```

## <a name="verifying-signatures"></a><span data-ttu-id="ee48b-117">Проверка подписей</span><span class="sxs-lookup"><span data-stu-id="ee48b-117">Verifying Signatures</span></span>

<span data-ttu-id="ee48b-118">Для проверки того, подписаны ли данные определенной стороной, необходимы следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="ee48b-118">To verify that data was signed by a particular party, you must have the following information:</span></span>

- <span data-ttu-id="ee48b-119">открытый ключ стороны, подписавшей данные;</span><span class="sxs-lookup"><span data-stu-id="ee48b-119">The public key of the party that signed the data.</span></span>

- <span data-ttu-id="ee48b-120">цифровая подпись;</span><span class="sxs-lookup"><span data-stu-id="ee48b-120">The digital signature.</span></span>

- <span data-ttu-id="ee48b-121">подписанные данные;</span><span class="sxs-lookup"><span data-stu-id="ee48b-121">The data that was signed.</span></span>

- <span data-ttu-id="ee48b-122">хэш-алгоритм, который использовался при создании подписи.</span><span class="sxs-lookup"><span data-stu-id="ee48b-122">The hash algorithm used by the signer.</span></span>

<span data-ttu-id="ee48b-123">Для проверки подписи, созданной с помощью класса <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> , используется класс <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> .</span><span class="sxs-lookup"><span data-stu-id="ee48b-123">To verify a signature signed by the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class, use the <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class.</span></span> <span data-ttu-id="ee48b-124">Классу <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> необходимо предоставить открытый ключ подписывающей стороны.</span><span class="sxs-lookup"><span data-stu-id="ee48b-124">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class must be supplied the public key of the signer.</span></span> <span data-ttu-id="ee48b-125">Для RSA потребуются значения модуля и экспоненты, чтобы указать открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="ee48b-125">For RSA, you will need the values of the modulus and the exponent to specify the public key.</span></span> <span data-ttu-id="ee48b-126">(Эти значения должны быть предоставлены стороной, создавшей пару открытого и закрытого ключей.) Сначала создайте <xref:System.Security.Cryptography.RSA> объект для хранения открытого ключа, который будет проверять подпись, а затем инициализирует <xref:System.Security.Cryptography.RSAParameters> структуру значениями модуля и экспоненты, задающих открытый ключ.</span><span class="sxs-lookup"><span data-stu-id="ee48b-126">(The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSA> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.</span></span>

<span data-ttu-id="ee48b-127">В следующем примере кода показано создание структуры <xref:System.Security.Cryptography.RSAParameters> .</span><span class="sxs-lookup"><span data-stu-id="ee48b-127">The following code shows the creation of an <xref:System.Security.Cryptography.RSAParameters> structure.</span></span> <span data-ttu-id="ee48b-128">Свойству `Modulus` присваивается байтовый массив `modulusData` , а свойству `Exponent` — байтовый массив `exponentData`.</span><span class="sxs-lookup"><span data-stu-id="ee48b-128">The `Modulus` property is set to the value of a byte array called `modulusData` and the `Exponent` property is set to the value of a byte array called `exponentData`.</span></span>

```vb
Dim rsaKeyInfo As RSAParameters
rsaKeyInfo.Modulus = modulusData
rsaKeyInfo.Exponent = exponentData
```

```csharp
RSAParameters rsaKeyInfo;
rsaKeyInfo.Modulus = modulusData;
rsaKeyInfo.Exponent = exponentData;
```

<span data-ttu-id="ee48b-129">После создания <xref:System.Security.Cryptography.RSAParameters> объекта можно инициализировать новый экземпляр класса реализации, применяя значения, <xref:System.Security.Cryptography.RSA> указанные в <xref:System.Security.Cryptography.RSAParameters> .</span><span class="sxs-lookup"><span data-stu-id="ee48b-129">After you have created the <xref:System.Security.Cryptography.RSAParameters> object, you can initialize a new instance of the <xref:System.Security.Cryptography.RSA> implementation class to the values specified in <xref:System.Security.Cryptography.RSAParameters>.</span></span> <span data-ttu-id="ee48b-130"><xref:System.Security.Cryptography.RSA>Экземпляр, в свою очередь, передается конструктору объекта <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> для передачи ключа.</span><span class="sxs-lookup"><span data-stu-id="ee48b-130">The <xref:System.Security.Cryptography.RSA> instance is, in turn, passed to the constructor of an <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> to transfer the key.</span></span>

<span data-ttu-id="ee48b-131">Этот процесс показан в приведенном ниже примере.</span><span class="sxs-lookup"><span data-stu-id="ee48b-131">The following example illustrates this process.</span></span> <span data-ttu-id="ee48b-132">В этом коде `hashValue` и `signedHashValue` — байтовые массивы, предоставленные удаленной стороной.</span><span class="sxs-lookup"><span data-stu-id="ee48b-132">In this example, `hashValue` and `signedHashValue` are arrays of bytes provided by a remote party.</span></span> <span data-ttu-id="ee48b-133">Удаленная сторона подписала объект `hashValue` с помощью алгоритма SHA1, создающего цифровую подпись `signedHashValue`.</span><span class="sxs-lookup"><span data-stu-id="ee48b-133">The remote party has signed the `hashValue` using the SHA1 algorithm, producing the digital signature `signedHashValue`.</span></span> <span data-ttu-id="ee48b-134"><xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType>Метод проверяет, является ли цифровая подпись допустимой и использовалась для подписывания `hashValue` .</span><span class="sxs-lookup"><span data-stu-id="ee48b-134">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `hashValue`.</span></span>

<span data-ttu-id="ee48b-135">Из-за проблем с алгоритмом SHA1 рекомендуется использовать SHA256 или более высокий уровень.</span><span class="sxs-lookup"><span data-stu-id="ee48b-135">Due to collision problems with SHA1, we recommend SHA256 or better.</span></span>  <span data-ttu-id="ee48b-136">Однако если для создания подписи использовался алгоритм SHA1, для проверки подписи необходимо использовать SHA1.</span><span class="sxs-lookup"><span data-stu-id="ee48b-136">However, if SHA1 was used to create the signature, you have to use SHA1 to verify the signature.</span></span>

```vb
Dim rsa As RSA = RSA.Create()
rsa.ImportParameters(rsaKeyInfo)
Dim rsaDeformatter As New RSAPKCS1SignatureDeformatter(rsa)
rsaDeformatter.SetHashAlgorithm("SHA1")
If rsaDeformatter.VerifySignature(hashValue, signedHashValue) Then
   Console.WriteLine("The signature is valid.")
Else
   Console.WriteLine("The signature is not valid.")
End If
```

```csharp
RSA rsa = RSA.Create();
rsa.ImportParameters(rsaKeyInfo);
RSAPKCS1SignatureDeformatter rsaDeformatter = new RSAPKCS1SignatureDeformatter(rsa);
rsaDeformatter.SetHashAlgorithm("SHA1");
if(rsaDeformatter.VerifySignature(hashValue, signedHashValue))
{
   Console.WriteLine("The signature is valid.");
}
else
{
   Console.WriteLine("The signature is not valid.");
}
```

<span data-ttu-id="ee48b-137">Если подпись действительна, этот фрагмент кода выдаст сообщение «`The signature is valid`», а в противном случае — сообщение «`The signature is not valid`».</span><span class="sxs-lookup"><span data-stu-id="ee48b-137">This code fragment will display "`The signature is valid`" if the signature is valid and "`The signature is not valid`" if it is not.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee48b-138">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="ee48b-138">See also</span></span>

- [<span data-ttu-id="ee48b-139">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="ee48b-139">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="ee48b-140">Модель криптографии</span><span class="sxs-lookup"><span data-stu-id="ee48b-140">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="ee48b-141">Кросс-платформенная криптография</span><span class="sxs-lookup"><span data-stu-id="ee48b-141">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="ee48b-142">ASP.NET Core Защита данных</span><span class="sxs-lookup"><span data-stu-id="ee48b-142">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)

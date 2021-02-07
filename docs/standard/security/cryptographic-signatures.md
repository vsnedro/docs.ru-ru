---
description: 'Дополнительные сведения: криптографические подписи'
title: Криптографические подписи
ms.date: 07/14/2020
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
ms.openlocfilehash: 082f55af648b73b6447d69edd5912804e9332d03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685300"
---
# <a name="cryptographic-signatures"></a>Криптографические подписи

Криптографические цифровые подписи используют алгоритмы с открытым ключом для обеспечения целостности данных. Если вы подписываете данные с помощью цифровой подписи, другая сторона может проверить подпись и убедиться в том, что данные поступили от вас и не были изменены после подписывания. Подробнее о цифровых подписях см. в разделе [Cryptographic Services](cryptographic-services.md).

В этом разделе описывается создание и проверка цифровых подписей с помощью классов пространства имен <xref:System.Security.Cryptography> .

## <a name="generating-signatures"></a>Создание подписей

Цифровые подписи обычно применяются к хэш-значениям, которые представляют массивы данных большого размера. В примере ниже демонстрируется применение цифровой подписи к хэш-значению. Сначала создается экземпляр класса <xref:System.Security.Cryptography.RSA> с целью формирования набора, состоящего из открытого и закрытого ключей. Затем экземпляр <xref:System.Security.Cryptography.RSA> передается в новый экземпляр класса <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> . При этом экземпляру <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>передается закрытый ключ, который и создает цифровую подпись. Перед тем как подписать хэш-код, вам необходимо указать используемый хэш-алгоритм. В этом примере используется алгоритм SHA1. Наконец, вызывается метод <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> для выполнения подписи.

Из-за проблем с алгоритмом SHA1 рекомендуется использовать SHA256 или более высокий уровень.

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

## <a name="verifying-signatures"></a>Проверка подписей

Для проверки того, подписаны ли данные определенной стороной, необходимы следующие сведения:

- открытый ключ стороны, подписавшей данные;

- цифровая подпись;

- подписанные данные;

- хэш-алгоритм, который использовался при создании подписи.

Для проверки подписи, созданной с помощью класса <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> , используется класс <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> . Классу <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> необходимо предоставить открытый ключ подписывающей стороны. Для RSA потребуются значения модуля и экспоненты, чтобы указать открытый ключ. (Эти значения должны быть предоставлены стороной, создавшей пару открытого и закрытого ключей.) Сначала создайте <xref:System.Security.Cryptography.RSA> объект для хранения открытого ключа, который будет проверять подпись, а затем инициализирует <xref:System.Security.Cryptography.RSAParameters> структуру значениями модуля и экспоненты, задающих открытый ключ.

В следующем примере кода показано создание структуры <xref:System.Security.Cryptography.RSAParameters> . Свойству `Modulus` присваивается байтовый массив `modulusData` , а свойству `Exponent` — байтовый массив `exponentData`.

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

После создания <xref:System.Security.Cryptography.RSAParameters> объекта можно инициализировать новый экземпляр класса реализации, применяя значения, <xref:System.Security.Cryptography.RSA> указанные в <xref:System.Security.Cryptography.RSAParameters> . <xref:System.Security.Cryptography.RSA>Экземпляр, в свою очередь, передается конструктору объекта <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> для передачи ключа.

Этот процесс показан в приведенном ниже примере. В этом коде `hashValue` и `signedHashValue` — байтовые массивы, предоставленные удаленной стороной. Удаленная сторона подписала объект `hashValue` с помощью алгоритма SHA1, создающего цифровую подпись `signedHashValue`. <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType>Метод проверяет, является ли цифровая подпись допустимой и использовалась для подписывания `hashValue` .

Из-за проблем с алгоритмом SHA1 рекомендуется использовать SHA256 или более высокий уровень.  Однако если для создания подписи использовался алгоритм SHA1, для проверки подписи необходимо использовать SHA1.

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

Если подпись действительна, этот фрагмент кода выдаст сообщение «`The signature is valid`», а в противном случае — сообщение «`The signature is not valid`».

## <a name="see-also"></a>См. также

- [службы шифрования](cryptographic-services.md)
- [Модель криптографии](cryptography-model.md)
- [Кросс-платформенная криптография](cross-platform-cryptography.md)
- [ASP.NET Core Защита данных](/aspnet/core/security/data-protection/introduction)

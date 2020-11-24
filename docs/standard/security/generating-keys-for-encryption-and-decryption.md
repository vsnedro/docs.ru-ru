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
# <a name="generating-keys-for-encryption-and-decryption"></a>Создание ключей для шифрования и расшифровки

Создание ключей и управление ими — это важная часть процесса шифрования. Симметричные алгоритмы требуют создания ключа и вектора инициализации (IV). Ключ следует хранить в тайне от любого, кто не должен расшифровывать ваши данные. Вектор инициализации может не быть секретным, но должен изменяться для каждого сеанса. Асимметричные алгоритмы требуют создания открытого ключа и закрытого ключа. Открытый ключ можно предоставлять кому угодно, а закрытый ключ должен быть известен только той стороне, которая будет расшифровывать данные, зашифрованные при помощи открытого ключа. В этом разделе описывается создание ключей и управление ими для симметричных и асимметричных алгоритмов.  
  
## <a name="symmetric-keys"></a>симметричные ключи;  

 Классы симметричного шифрования, предоставляемые .NET, нуждаются в ключе и новом векторе инициализации (IV) для шифрования и расшифровки данных. При создании нового экземпляра одного из управляемых симметричных криптографических классов с помощью метода без параметров `Create()` автоматически создаются новый ключ и вектор инициализации. Все пользователи, которым вы разрешаете расшифровывать свои данные, должны иметь тот же ключ и вектора инициализации и использовать тот же алгоритм. Как правило, новый ключ и вектор инициализации должны создаваться для каждого сеанса, и ни вектор инициализации, ни ключ нельзя сохранять для использования в следующем сеансе.  
  
 При передаче симметричного ключа и вектора инициализации на удаленную сторону симметричный ключ обычно шифруется с помощью асимметричного шифрования. Отправка ключа через незащищенную сеть без шифрования небезопасна, так как любой, кто перехватит ключ и вектор инициализации, сможет расшифровать данные.  
  
 В следующем примере показано создание нового экземпляра класса реализации по умолчанию для <xref:System.Security.Cryptography.Aes> алгоритма.  
  
```vb  
Dim aes As Aes = Aes.Create()  
```  
  
```csharp  
Aes aes = Aes.Create();  
```  
  
 При выполнении предыдущего кода осуществляется создание нового ключа и вектора инициализации и их помещение в свойства **Key** и **IV** соответственно.  
  
 Иногда может понадобиться создать несколько ключей. В этом случае можно создать новый экземпляр класса, реализующий симметричный алгоритм, а затем создать новый ключ и вектор инициализации, вызвав методы **GenerateKey** и **GenerateIV** . В следующем примере кода показано, как создать новые ключи и IVs после внесения нового экземпляра симметричного криптографического класса.  
  
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
  
 При выполнении приведенного выше кода ключ и вектор инициализации создаются при создании нового экземпляра **AES** . Другой ключ и вектор инициализации создаются при вызове методов **GenerateKey** и **GenerateIV** .
  
## <a name="asymmetric-keys"></a>Асимметричные ключи

 .NET предоставляет <xref:System.Security.Cryptography.RSA> класс для асимметричного шифрования. Этот класс создает пару открытого и закрытого ключей при использовании метода без параметров `Create()` для создания нового экземпляра. Асимметричные ключи можно сохранять для использования в нескольких сеансах или создавать только для отдельного сеанса. В то время как открытый ключ можно сделать общедоступным, закрытый ключ должен быть надежно защищен.  
  
 Пара из открытого и закрытого ключей создается каждый раз, когда создается новый экземпляр класса асимметричного алгоритма. После создания нового экземпляра класса сведения о ключе можно извлечь с помощью <xref:System.Security.Cryptography.RSA.ExportParameters%2A> метода, который возвращает <xref:System.Security.Cryptography.RSAParameters> структуру, содержащую сведения о ключе. Метод принимает логическое значение, указывающее, следует ли возвращать только сведения об открытом ключе или как сведения об открытом ключе, так и о закрытом ключе.

Существуют также и другие методы, позволяющие извлекать ключевые сведения, например:

* <xref:System.Security.Cryptography.RSA.ExportRSAPublicKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.RSA.ExportRSAPrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportSubjectPublicKeyInfo%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportPkcs8PrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportEncryptedPkcs8PrivateKey%2A?displayProperty=nameWithType>

Экземпляр **RSA** можно инициализировать со значением структуры **RSAParameters** с помощью <xref:System.Security.Cryptography.RSA.ImportParameters%2A> метода. Или создайте новый экземпляр с помощью <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> метода.  
  
 Асимметричные закрытые ключи никогда не следует хранить буквальной форме или в формате обычного текста на локальном компьютере. Если необходимо хранить закрытый ключ, следует использовать для этого контейнер ключа. Дополнительные сведения о хранении закрытого ключа в контейнере ключей см. в разделе [как хранить асимметричные ключи в контейнере ключей](how-to-store-asymmetric-keys-in-a-key-container.md).  
  
 В следующем примере кода создается новый экземпляр класса **RSA** , который создает пару из открытого и закрытого ключей и сохраняет сведения об открытом ключе в структуре **RSAParameters** .  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Шифрование данных](encrypting-data.md)
- [Расшифровка данных](decrypting-data.md)
- [службы шифрования](cryptographic-services.md)
- [Практическое руководство. Хранение асимметричных ключей в контейнере ключей](how-to-store-asymmetric-keys-in-a-key-container.md)
- [Кросс-платформенная криптография](cross-platform-cryptography.md)
- [ASP.NET Core Защита данных](/aspnet/core/security/data-protection/introduction)

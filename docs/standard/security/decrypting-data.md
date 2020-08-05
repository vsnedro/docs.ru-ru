---
title: Расшифровка данных
description: Узнайте, как расшифровать данные в .NET с помощью симметричного алгоритма или асимметричного алгоритма.
ms.date: 07/16/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: 2ba4c3ba43d688aeb66c67ec3f94f4a503d47892
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556986"
---
# <a name="decrypting-data"></a><span data-ttu-id="e5084-103">Расшифровка данных</span><span class="sxs-lookup"><span data-stu-id="e5084-103">Decrypting Data</span></span>

<span data-ttu-id="e5084-104">Расшифровка представляет собой операцию, обратную операции шифрования.</span><span class="sxs-lookup"><span data-stu-id="e5084-104">Decryption is the reverse operation of encryption.</span></span> <span data-ttu-id="e5084-105">Для шифрования с секретным ключом необходимо знать как ключ, так и вектор инициализации, которые использовались при шифровании данных.</span><span class="sxs-lookup"><span data-stu-id="e5084-105">For secret-key encryption, you must know both the key and IV that were used to encrypt the data.</span></span> <span data-ttu-id="e5084-106">Для шифрования с открытым ключом необходимо знать либо открытый ключ (если данные были зашифрованы при помощи закрытого ключа), либо закрытый ключ (если данные были зашифрованы при помощи открытого ключа).</span><span class="sxs-lookup"><span data-stu-id="e5084-106">For public-key encryption, you must know either the public key (if the data was encrypted using the private key) or the private key (if the data was encrypted using the public key).</span></span>

## <a name="symmetric-decryption"></a><span data-ttu-id="e5084-107">Симметричная расшифровка</span><span class="sxs-lookup"><span data-stu-id="e5084-107">Symmetric Decryption</span></span>

<span data-ttu-id="e5084-108">Расшифровка данных, зашифрованных при помощи симметричных алгоритмов, похожа на процесс, используемый для шифрования данных при помощи симметричных алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="e5084-108">The decryption of data encrypted with symmetric algorithms is similar to the process used to encrypt data with symmetric algorithms.</span></span> <span data-ttu-id="e5084-109"><xref:System.Security.Cryptography.CryptoStream>Класс используется с симметричными криптографическими классами, предоставляемыми .NET для расшифровки данных, считанных из любого управляемого объекта потока.</span><span class="sxs-lookup"><span data-stu-id="e5084-109">The <xref:System.Security.Cryptography.CryptoStream> class is used with symmetric cryptography classes provided by .NET to decrypt data read from any managed stream object.</span></span>

<span data-ttu-id="e5084-110">В следующем примере показано, как создать новый экземпляр класса реализации по умолчанию для <xref:System.Security.Cryptography.Aes> алгоритма.</span><span class="sxs-lookup"><span data-stu-id="e5084-110">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="e5084-111">Экземпляр используется для расшифровки <xref:System.Security.Cryptography.CryptoStream> объекта.</span><span class="sxs-lookup"><span data-stu-id="e5084-111">The instance is used to perform decryption on a <xref:System.Security.Cryptography.CryptoStream> object.</span></span> <span data-ttu-id="e5084-112">В этом примере сначала создается новый экземпляр класса реализации **AES** .</span><span class="sxs-lookup"><span data-stu-id="e5084-112">This example first creates a new instance of the **Aes** implementation class.</span></span> <span data-ttu-id="e5084-113">Затем он создает объект **CryptoStream** и инициализирует его значением управляемого потока, вызвавшего `myStream`.</span><span class="sxs-lookup"><span data-stu-id="e5084-113">Next it creates a **CryptoStream** object and initializes it to the value of a managed stream called `myStream`.</span></span> <span data-ttu-id="e5084-114">Затем методу **CreateDecryptor** из класса **AES** передается тот же ключ и вектор инициализации, которые использовались для шифрования, а затем передаются в конструктор **CryptoStream** .</span><span class="sxs-lookup"><span data-stu-id="e5084-114">Next, the **CreateDecryptor** method from the **Aes** class is passed the same key and IV that was used for encryption and is then passed to the **CryptoStream** constructor.</span></span>

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

<span data-ttu-id="e5084-115">В следующем примере показан весь процесс создания потока, расшифровки потока, чтения из потока и закрытия потока.</span><span class="sxs-lookup"><span data-stu-id="e5084-115">The following example shows the entire process of creating a stream, decrypting the stream, reading from the stream, and closing the streams.</span></span> <span data-ttu-id="e5084-116">Создается объект файлового потока, который считывает файл с именем *TestData.txt*.</span><span class="sxs-lookup"><span data-stu-id="e5084-116">A file stream object is created that reads a file named *TestData.txt*.</span></span> <span data-ttu-id="e5084-117">Затем файловый поток расшифровывается с помощью класса **CryptoStream** и класса **AES** .</span><span class="sxs-lookup"><span data-stu-id="e5084-117">The file stream is then decrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="e5084-118">В этом примере указываются значения ключа и вектора инициализации, используемые в примере симметричного шифрования для [шифрования данных](encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="e5084-118">This example specifies key and IV values that are used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="e5084-119">Он не показывает код, необходимый для шифрования и передачи этих значений.</span><span class="sxs-lookup"><span data-stu-id="e5084-119">It does not show the code needed to encrypt and transfer these values.</span></span>

```vb
Imports System
Imports System.IO
Imports System.Security.Cryptography

Module Module1
    Sub Main()
            'The key and IV must be the same values that were used
            'to encrypt the stream.
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
        Try
            'Create a file stream.
            Dim myStream As FileStream = new FileStream("TestData.txt", FileMode.Open)

            'Create a new instance of the default Aes implementation class
            'and decrypt the stream.
            Dim aes As Aes = Aes.Create()

            'Create an instance of the CryptoStream class, pass it the file stream, and decrypt
            'it with the Rijndael class using the key and IV.
            Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)

            'Read the stream.
            Dim sReader As New StreamReader(cryptStream)

            'Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd())

            'Close the streams.
            sReader.Close()
            myStream.Close()
            'Catch any exceptions.
        Catch
            Console.WriteLine("The decryption Failed.")
            Throw
        End Try
    End Sub
End Module
```

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

class Class1
{
    static void Main(string[] args)
    {
        //The key and IV must be the same values that were used
        //to encrypt the stream.
        byte[] key = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16 };
        byte[] iv = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16 };
        try
        {
            //Create a file stream.
            FileStream myStream = new FileStream("TestData.txt", FileMode.Open);

            //Create a new instance of the default Aes implementation class
            Aes aes = Aes.Create();

            //Create a CryptoStream, pass it the file stream, and decrypt
            //it with the Aes class using the key and IV.
            CryptoStream cryptStream = new CryptoStream(
               myStream,
               aes.CreateDecryptor(key, iv),
               CryptoStreamMode.Read);

            //Read the stream.
            StreamReader sReader = new StreamReader(cryptStream);

            //Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd());

            //Close the streams.
            sReader.Close();
            myStream.Close();
        }
        //Catch any exceptions.
        catch
        {
            Console.WriteLine("The decryption failed.");
            throw;
        }
    }
}
```

<span data-ttu-id="e5084-120">В предыдущем примере используется тот же ключ, IV и алгоритм, который использовался в примере симметричного шифрования для [шифрования данных](encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="e5084-120">The preceding example uses the same key, IV, and algorithm used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="e5084-121">Он расшифровывает файл *TestData.txt* , созданный в этом примере, и отображает исходный текст в консоли.</span><span class="sxs-lookup"><span data-stu-id="e5084-121">It decrypts the *TestData.txt* file that is created by that example and displays the original text on the console.</span></span>

## <a name="asymmetric-decryption"></a><span data-ttu-id="e5084-122">Асимметричная расшифровка</span><span class="sxs-lookup"><span data-stu-id="e5084-122">Asymmetric Decryption</span></span>

<span data-ttu-id="e5084-123">Как правило, сторона (сторона А) создает как открытый, так и закрытый ключи и сохраняет их в памяти или в контейнере криптографических ключей.</span><span class="sxs-lookup"><span data-stu-id="e5084-123">Typically, a party (party A) generates both a public and private key and stores the key either in memory or in a cryptographic key container.</span></span> <span data-ttu-id="e5084-124">Затем сторона А пересылает открытый ключ другой стороне (сторона Б).</span><span class="sxs-lookup"><span data-stu-id="e5084-124">Party A then sends the public key to another party (party B).</span></span> <span data-ttu-id="e5084-125">С помощью открытого ключа сторона б шифрует данные и отправляет их обратно стороне A. После получения данных сторона A расшифровывает их с помощью закрытого ключа, который соответствует.</span><span class="sxs-lookup"><span data-stu-id="e5084-125">Using the public key, party B encrypts data and sends the data back to party A. After receiving the data, party A decrypts it using the private key that corresponds.</span></span> <span data-ttu-id="e5084-126">Расшифровка будет успешной только в том случае, если сторона А использует закрытый ключ, соответствующий открытому ключу, использованному стороной Б для шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="e5084-126">Decryption will be successful only if party A uses the private key that corresponds to the public key Party B used to encrypt the data.</span></span>

<span data-ttu-id="e5084-127">Дополнительные сведения о хранении асимметричных ключей в безопасном контейнере криптографических ключей и последующем извлечении асимметричного ключа см. в разделе [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span><span class="sxs-lookup"><span data-stu-id="e5084-127">For information on how to store an asymmetric key in secure cryptographic key container and how to later retrieve the asymmetric key, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>

<span data-ttu-id="e5084-128">Следующий пример иллюстрирует расшифровку двух массивов байтов, представляющих симметричный ключ и вектор инициализации.</span><span class="sxs-lookup"><span data-stu-id="e5084-128">The following example illustrates the decryption of two arrays of bytes that represent a symmetric key and IV.</span></span> <span data-ttu-id="e5084-129">Дополнительные сведения о способе извлечения асимметричного открытого ключа из объекта <xref:System.Security.Cryptography.RSA> в формате, допускающем простую отправку третьей стороне, см. в разделе [Encrypting Data](encrypting-data.md).</span><span class="sxs-lookup"><span data-stu-id="e5084-129">For information on how to extract the asymmetric public key from the <xref:System.Security.Cryptography.RSA> object in a format that you can easily send to a third party, see [Encrypting Data](encrypting-data.md).</span></span>

```vb
'Create a new instance of the RSA class.
Dim rsa As RSA = RSA.Create()

' Export the public key information and send it to a third party.
' Wait for the third party to encrypt some data and send it back.

'Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1)
symmetricIV = rsa.Decrypt(encryptedSymmetricIV, RSAEncryptionPadding.Pkcs1)
```

```csharp
//Create a new instance of the RSA class.
RSA rsa = RSA.Create();

// Export the public key information and send it to a third party.
// Wait for the third party to encrypt some data and send it back.

//Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1);
symmetricIV = rsa.Decrypt(encryptedSymmetricIV , RSAEncryptionPadding.Pkcs1);
```

## <a name="see-also"></a><span data-ttu-id="e5084-130">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e5084-130">See also</span></span>

- [<span data-ttu-id="e5084-131">Создание ключей для шифрования и расшифровки</span><span class="sxs-lookup"><span data-stu-id="e5084-131">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="e5084-132">Шифрование данных</span><span class="sxs-lookup"><span data-stu-id="e5084-132">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="e5084-133">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="e5084-133">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="e5084-134">Модель криптографии</span><span class="sxs-lookup"><span data-stu-id="e5084-134">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="e5084-135">Кросс-платформенная криптография</span><span class="sxs-lookup"><span data-stu-id="e5084-135">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="e5084-136">Уязвимости в учете времени при симметричной расшифровке в режиме CBC с использованием заполнения</span><span class="sxs-lookup"><span data-stu-id="e5084-136">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="e5084-137">ASP.NET Core Защита данных</span><span class="sxs-lookup"><span data-stu-id="e5084-137">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)

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
# <a name="decrypting-data"></a>Расшифровка данных

Расшифровка представляет собой операцию, обратную операции шифрования. Для шифрования с секретным ключом необходимо знать как ключ, так и вектор инициализации, которые использовались при шифровании данных. Для шифрования с открытым ключом необходимо знать либо открытый ключ (если данные были зашифрованы при помощи закрытого ключа), либо закрытый ключ (если данные были зашифрованы при помощи открытого ключа).

## <a name="symmetric-decryption"></a>Симметричная расшифровка

Расшифровка данных, зашифрованных при помощи симметричных алгоритмов, похожа на процесс, используемый для шифрования данных при помощи симметричных алгоритмов. <xref:System.Security.Cryptography.CryptoStream>Класс используется с симметричными криптографическими классами, предоставляемыми .NET для расшифровки данных, считанных из любого управляемого объекта потока.

В следующем примере показано, как создать новый экземпляр класса реализации по умолчанию для <xref:System.Security.Cryptography.Aes> алгоритма. Экземпляр используется для расшифровки <xref:System.Security.Cryptography.CryptoStream> объекта. В этом примере сначала создается новый экземпляр класса реализации **AES** . Затем он создает объект **CryptoStream** и инициализирует его значением управляемого потока, вызвавшего `myStream`. Затем методу **CreateDecryptor** из класса **AES** передается тот же ключ и вектор инициализации, которые использовались для шифрования, а затем передаются в конструктор **CryptoStream** .

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

В следующем примере показан весь процесс создания потока, расшифровки потока, чтения из потока и закрытия потока. Создается объект файлового потока, который считывает файл с именем *TestData.txt*. Затем файловый поток расшифровывается с помощью класса **CryptoStream** и класса **AES** . В этом примере указываются значения ключа и вектора инициализации, используемые в примере симметричного шифрования для [шифрования данных](encrypting-data.md). Он не показывает код, необходимый для шифрования и передачи этих значений.

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

В предыдущем примере используется тот же ключ, IV и алгоритм, который использовался в примере симметричного шифрования для [шифрования данных](encrypting-data.md). Он расшифровывает файл *TestData.txt* , созданный в этом примере, и отображает исходный текст в консоли.

## <a name="asymmetric-decryption"></a>Асимметричная расшифровка

Как правило, сторона (сторона А) создает как открытый, так и закрытый ключи и сохраняет их в памяти или в контейнере криптографических ключей. Затем сторона А пересылает открытый ключ другой стороне (сторона Б). С помощью открытого ключа сторона б шифрует данные и отправляет их обратно стороне A. После получения данных сторона A расшифровывает их с помощью закрытого ключа, который соответствует. Расшифровка будет успешной только в том случае, если сторона А использует закрытый ключ, соответствующий открытому ключу, использованному стороной Б для шифрования данных.

Дополнительные сведения о хранении асимметричных ключей в безопасном контейнере криптографических ключей и последующем извлечении асимметричного ключа см. в разделе [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).

Следующий пример иллюстрирует расшифровку двух массивов байтов, представляющих симметричный ключ и вектор инициализации. Дополнительные сведения о способе извлечения асимметричного открытого ключа из объекта <xref:System.Security.Cryptography.RSA> в формате, допускающем простую отправку третьей стороне, см. в разделе [Encrypting Data](encrypting-data.md).

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

## <a name="see-also"></a>См. также раздел

- [Создание ключей для шифрования и расшифровки](generating-keys-for-encryption-and-decryption.md)
- [Шифрование данных](encrypting-data.md)
- [службы шифрования](cryptographic-services.md)
- [Модель криптографии](cryptography-model.md)
- [Кросс-платформенная криптография](cross-platform-cryptography.md)
- [Уязвимости в учете времени при симметричной расшифровке в режиме CBC с использованием заполнения](vulnerabilities-cbc-mode.md)
- [ASP.NET Core Защита данных](/aspnet/core/security/data-protection/introduction)

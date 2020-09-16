---
title: Как хранить асимметричные ключи в контейнере ключей
description: Сведения о хранении асимметричных ключей в контейнере ключей в .NET. Узнайте, как создать асимметричный ключ, сохранить его в контейнере ключей и извлечь и удалить ключ.
ms.date: 05/26/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], asymmetric keys
- storing asymmetric keys
- keys, asymmetric
- encryption keys
- keys, storing in key containers
- asymmetric keys [.NET]
- encryption [.NET], asymmetric keys
- decryption keys
ms.assetid: 0dbcbd8d-0dcf-40e9-9f0c-e3f162d35ccc
ms.openlocfilehash: c0e0904089c4b7054aa3ef7510c20e40c57dc733
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554414"
---
# <a name="store-asymmetric-keys-in-a-key-container"></a>Хранение асимметричных ключей в контейнере ключей

Асимметричные закрытые ключи никогда не следует хранить буквальной форме или в формате обычного текста на локальном компьютере. Если необходимо сохранить закрытый ключ, используйте контейнер ключей. Дополнительные сведения о контейнерах ключей см. в разделе [Основные сведения о контейнерах ключей RSA уровня компьютера и пользователя](/previous-versions/aspnet/f5cs0acs(v=vs.100)).

> [!NOTE]
> Код в этой статье относится к Windows и использует функции, недоступные в .NET Core 2,2 и более ранних версиях. Дополнительные сведения см. в разделе [DotNet/Runtime # 23391](https://github.com/dotnet/runtime/issues/23391).

## <a name="create-an-asymmetric-key-and-save-it-in-a-key-container"></a>Создайте асимметричный ключ и сохраните его в контейнере ключей.

1. Создайте новый экземпляр <xref:System.Security.Cryptography.CspParameters> класса и передайте в поле имя, которое необходимо вызвать для вызова контейнера ключей <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> .

1. Создайте новый экземпляр класса, производного от <xref:System.Security.Cryptography.AsymmetricAlgorithm> класса (обычно <xref:System.Security.Cryptography.RSACryptoServiceProvider> или <xref:System.Security.Cryptography.DSACryptoServiceProvider> ), и передайте созданный ранее `CspParameters` объект в его конструктор.

> [!NOTE]
> Создание и извлечение асимметричного ключа — это одна операция. Если ключ еще не находится в контейнере, он создается перед возвратом.
>
> - <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType>
> - <xref:System.Security.Cryptography.DSA.ToXmlString%2A?displayProperty=nameWithType>

## <a name="delete-the-key-from-the-key-container"></a>Удаление ключа из контейнера ключей

1. Создайте новый экземпляр `CspParameters` класса и передайте в поле имя, которое необходимо вызвать для вызова контейнера ключей <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> .

1. Создайте новый экземпляр класса, производного от <xref:System.Security.Cryptography.AsymmetricAlgorithm> класса (обычно `RSACryptoServiceProvider` или `DSACryptoServiceProvider` ), и передайте созданный ранее `CspParameters` объект в его конструктор.

1. Задайте <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> для свойства или класса, производного от, значение `AsymmetricAlgorithm` `false` ( `False` в Visual Basic).

1. Вызовите `Clear` метод класса, производного от `AsymmetricAlgorithm` . Этот метод освобождает все ресурсы класса и очищает контейнер ключей.

## <a name="example"></a>Пример

В следующем примере показано, как создать асимметричный ключ, сохранить его в контейнере ключей, затем извлечь ключ и удалить его из контейнера.

Обратите внимание, что код в методах `GenKey_SaveInContainer` и `GetKeyFromContainer` совпадает. При указании имени контейнера ключей для <xref:System.Security.Cryptography.CspParameters> объекта и передаче его <xref:System.Security.Cryptography.AsymmetricAlgorithm> объекту со <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> свойством или <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> свойством, имеющим значение `true` , поведение будет следующим:

- Если контейнер ключей с указанным именем не существует, он создается, а ключ сохраняется.
- Если контейнер ключей с указанным именем существует, то ключ в этом контейнере автоматически загружается в текущий объект <xref:System.Security.Cryptography.AsymmetricAlgorithm>.

Поэтому код в `GenKey_SaveInContainer` методе сохраняет ключ, так как он выполняется первым, а код в `GetKeyFromContainer` методе загружает ключ, так как он выполняется во второй.

```vb
Imports System
Imports System.Security.Cryptography

Public Class StoreKey

    Public Shared Sub Main()
        Try
            ' Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer")

            ' Retrieve the key from the container.
            GetKeyFromContainer("MyKeyContainer")

            ' Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer")

            ' Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer")

            ' Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer")
        Catch e As CryptographicException
            Console.WriteLine(e.Message)
        End Try
    End Sub

    Private Shared Sub GenKey_SaveInContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        ' name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key added to container:  {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub GetKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container MyKeyContainerName.
        Using rsa As New RSACryptoServiceProvider(parameters)
            ' Display the key information to the console.
            Console.WriteLine($"Key retrieved from container : {rsa.ToXmlString(True)}")
        End Using
    End Sub

    Private Shared Sub DeleteKeyFromContainer(ByVal ContainerName As String)
        ' Create the CspParameters object and set the key container
        '  name used to store the RSA key pair.
        Dim parameters As New CspParameters With {
            .KeyContainerName = ContainerName
        }

        ' Create a new instance of RSACryptoServiceProvider that accesses
        ' the key container.
        ' Delete the key entry in the container.
        Dim rsa As New RSACryptoServiceProvider(parameters) With {
            .PersistKeyInCsp = False
        }

        ' Call Clear to release resources and delete the key from the container.
        rsa.Clear()

        Console.WriteLine("Key deleted.")
    End Sub
End Class
```

```csharp
using System;
using System.Security.Cryptography;

public class StoreKey
{
    public static void Main()
    {
        try
        {
            // Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer");

            // Retrieve the key from the container.
            GetKeyFromContainer("MyKeyContainer");

            // Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer");

            // Create a key and save it in a container.
            GenKey_SaveInContainer("MyKeyContainer");

            // Delete the key from the container.
            DeleteKeyFromContainer("MyKeyContainer");
        }
        catch (CryptographicException e)
        {
            Console.WriteLine(e.Message);
        }
    }

    private static void GenKey_SaveInContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key added to container: \n  {rsa.ToXmlString(true)}");
    }

    private static void GetKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container MyKeyContainerName.
        using var rsa = new RSACryptoServiceProvider(parameters);

        // Display the key information to the console.
        Console.WriteLine($"Key retrieved from container : \n {rsa.ToXmlString(true)}");
    }

    private static void DeleteKeyFromContainer(string containerName)
    {
        // Create the CspParameters object and set the key container
        // name used to store the RSA key pair.
        var parameters = new CspParameters
        {
            KeyContainerName = containerName
        };

        // Create a new instance of RSACryptoServiceProvider that accesses
        // the key container.
        using var rsa = new RSACryptoServiceProvider(parameters)
        {
            // Delete the key entry in the container.
            PersistKeyInCsp = false
        };

        // Call Clear to release resources and delete the key from the container.
        rsa.Clear();

        Console.WriteLine("Key deleted.");
    }
}
```

Вывод выглядит следующим образом.

```console
Key added to container:
<RSAKeyValue> Key Information A</RSAKeyValue>
Key retrieved from container :
<RSAKeyValue> Key Information A</RSAKeyValue>
Key deleted.
Key added to container:
<RSAKeyValue> Key Information B</RSAKeyValue>
Key deleted.
```

## <a name="see-also"></a>См. также

- [Модель криптографии](cryptography-model.md)
- [службы шифрования](cryptographic-services.md)
- [Кросс-платформенная криптография](cross-platform-cryptography.md)
- [Создание ключей для шифрования и расшифровки](generating-keys-for-encryption-and-decryption.md)
- [Шифрование данных](encrypting-data.md)
- [Расшифровка данных](decrypting-data.md)
- [ASP.NET Core Защита данных](/aspnet/core/security/data-protection/introduction)

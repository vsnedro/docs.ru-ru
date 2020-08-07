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
ms.openlocfilehash: 9c04d1ea4d7e7ee46d875b3fa791f3eee2059e52
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "87854728"
---
# <a name="store-asymmetric-keys-in-a-key-container"></a><span data-ttu-id="38912-104">Хранение асимметричных ключей в контейнере ключей</span><span class="sxs-lookup"><span data-stu-id="38912-104">Store asymmetric keys in a key container</span></span>

<span data-ttu-id="38912-105">Асимметричные закрытые ключи никогда не следует хранить буквальной форме или в формате обычного текста на локальном компьютере.</span><span class="sxs-lookup"><span data-stu-id="38912-105">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="38912-106">Если необходимо сохранить закрытый ключ, используйте контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="38912-106">If you need to store a private key, use a key container.</span></span> <span data-ttu-id="38912-107">Дополнительные сведения о контейнерах ключей см. в разделе [Основные сведения о контейнерах ключей RSA уровня компьютера и пользователя](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="38912-107">For more information on key containers, see [Understanding machine-level and user-level RSA key containers](https://docs.microsoft.com/previous-versions/aspnet/f5cs0acs(v=vs.100)).</span></span>

> [!NOTE]
> <span data-ttu-id="38912-108">Код в этой статье относится к Windows и использует функции, недоступные в .NET Core 2,2 и более ранних версиях.</span><span class="sxs-lookup"><span data-stu-id="38912-108">The code in this article applies to Windows and uses features not available in .NET Core 2.2 and earlier versions.</span></span> <span data-ttu-id="38912-109">Дополнительные сведения см. в разделе [DotNet/Runtime # 23391](https://github.com/dotnet/runtime/issues/23391).</span><span class="sxs-lookup"><span data-stu-id="38912-109">For more information, see [dotnet/runtime#23391](https://github.com/dotnet/runtime/issues/23391).</span></span>

## <a name="create-an-asymmetric-key-and-save-it-in-a-key-container"></a><span data-ttu-id="38912-110">Создайте асимметричный ключ и сохраните его в контейнере ключей.</span><span class="sxs-lookup"><span data-stu-id="38912-110">Create an asymmetric key and save it in a key container</span></span>

1. <span data-ttu-id="38912-111">Создайте новый экземпляр <xref:System.Security.Cryptography.CspParameters> класса и передайте в поле имя, которое необходимо вызвать для вызова контейнера ключей <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="38912-111">Create a new instance of a <xref:System.Security.Cryptography.CspParameters> class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="38912-112">Создайте новый экземпляр класса, производного от <xref:System.Security.Cryptography.AsymmetricAlgorithm> класса (обычно <xref:System.Security.Cryptography.RSACryptoServiceProvider> или <xref:System.Security.Cryptography.DSACryptoServiceProvider> ), и передайте созданный ранее `CspParameters` объект в его конструктор.</span><span class="sxs-lookup"><span data-stu-id="38912-112">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually <xref:System.Security.Cryptography.RSACryptoServiceProvider> or <xref:System.Security.Cryptography.DSACryptoServiceProvider>) and pass the previously created `CspParameters` object to its constructor.</span></span>

> [!NOTE]
> <span data-ttu-id="38912-113">Создание и извлечение асимметричного ключа — это одна операция.</span><span class="sxs-lookup"><span data-stu-id="38912-113">The creation and retrieval of an asymmetric key is one operation.</span></span> <span data-ttu-id="38912-114">Если ключ еще не находится в контейнере, он создается перед возвратом.</span><span class="sxs-lookup"><span data-stu-id="38912-114">If a key is not already in the container, it's created before being returned.</span></span>
>
> - <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType>
> - <xref:System.Security.Cryptography.DSA.ToXmlString%2A?displayProperty=nameWithType>

## <a name="delete-the-key-from-the-key-container"></a><span data-ttu-id="38912-115">Удаление ключа из контейнера ключей</span><span class="sxs-lookup"><span data-stu-id="38912-115">Delete the key from the key container</span></span>

1. <span data-ttu-id="38912-116">Создайте новый экземпляр `CspParameters` класса и передайте в поле имя, которое необходимо вызвать для вызова контейнера ключей <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="38912-116">Create a new instance of a `CspParameters` class and pass the name that you want to call the key container to the <xref:System.Security.Cryptography.CspParameters.KeyContainerName?displayProperty=nameWithType> field.</span></span>

1. <span data-ttu-id="38912-117">Создайте новый экземпляр класса, производного от <xref:System.Security.Cryptography.AsymmetricAlgorithm> класса (обычно `RSACryptoServiceProvider` или `DSACryptoServiceProvider` ), и передайте созданный ранее `CspParameters` объект в его конструктор.</span><span class="sxs-lookup"><span data-stu-id="38912-117">Create a new instance of a class that derives from the <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (usually `RSACryptoServiceProvider` or `DSACryptoServiceProvider`) and pass the previously created `CspParameters` object to its constructor.</span></span>

1. <span data-ttu-id="38912-118">Задайте <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> для свойства или класса, производного от, значение `AsymmetricAlgorithm` `false` ( `False` в Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="38912-118">Set the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> or the <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp?displayProperty=nameWithType> property of the class that derives from `AsymmetricAlgorithm` to `false` (`False` in Visual Basic).</span></span>

1. <span data-ttu-id="38912-119">Вызовите `Clear` метод класса, производного от `AsymmetricAlgorithm` .</span><span class="sxs-lookup"><span data-stu-id="38912-119">Call the `Clear` method of the class that derives from `AsymmetricAlgorithm`.</span></span> <span data-ttu-id="38912-120">Этот метод освобождает все ресурсы класса и очищает контейнер ключей.</span><span class="sxs-lookup"><span data-stu-id="38912-120">This method releases all resources of the class and clears the key container.</span></span>

## <a name="example"></a><span data-ttu-id="38912-121">Пример</span><span class="sxs-lookup"><span data-stu-id="38912-121">Example</span></span>

<span data-ttu-id="38912-122">В следующем примере показано, как создать асимметричный ключ, сохранить его в контейнере ключей, затем извлечь ключ и удалить его из контейнера.</span><span class="sxs-lookup"><span data-stu-id="38912-122">The following example demonstrates how to create an asymmetric key, save it in a key container, retrieve the key at a later time, and delete the key from the container.</span></span>

<span data-ttu-id="38912-123">Обратите внимание, что код в методах `GenKey_SaveInContainer` и `GetKeyFromContainer` совпадает.</span><span class="sxs-lookup"><span data-stu-id="38912-123">Notice that code in the `GenKey_SaveInContainer` method and the `GetKeyFromContainer` method is similar.</span></span> <span data-ttu-id="38912-124">При указании имени контейнера ключей для <xref:System.Security.Cryptography.CspParameters> объекта и передаче его <xref:System.Security.Cryptography.AsymmetricAlgorithm> объекту со <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> свойством или <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> свойством, имеющим значение `true` , поведение будет следующим:</span><span class="sxs-lookup"><span data-stu-id="38912-124">When you specify a key container name for a <xref:System.Security.Cryptography.CspParameters> object and pass it to an <xref:System.Security.Cryptography.AsymmetricAlgorithm> object with the <xref:System.Security.Cryptography.RSACryptoServiceProvider.PersistKeyInCsp%2A> property or <xref:System.Security.Cryptography.DSACryptoServiceProvider.PersistKeyInCsp%2A> property set to `true`, the behavior is as follows:</span></span>

- <span data-ttu-id="38912-125">Если контейнер ключей с указанным именем не существует, он создается, а ключ сохраняется.</span><span class="sxs-lookup"><span data-stu-id="38912-125">If a key container with the specified name does not exist, then one is created and the key is persisted.</span></span>
- <span data-ttu-id="38912-126">Если контейнер ключей с указанным именем существует, то ключ в этом контейнере автоматически загружается в текущий объект <xref:System.Security.Cryptography.AsymmetricAlgorithm>.</span><span class="sxs-lookup"><span data-stu-id="38912-126">If a key container with the specified name does exist, then the key in the container is automatically loaded into the current <xref:System.Security.Cryptography.AsymmetricAlgorithm> object.</span></span>

<span data-ttu-id="38912-127">Поэтому код в `GenKey_SaveInContainer` методе сохраняет ключ, так как он выполняется первым, а код в `GetKeyFromContainer` методе загружает ключ, так как он выполняется во второй.</span><span class="sxs-lookup"><span data-stu-id="38912-127">Therefore, the code in the `GenKey_SaveInContainer` method persists the key because it is run first, while the code in the `GetKeyFromContainer` method loads the key because it's run second.</span></span>

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

<span data-ttu-id="38912-128">Вывод выглядит следующим образом.</span><span class="sxs-lookup"><span data-stu-id="38912-128">The output is as follows:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="38912-129">См. также</span><span class="sxs-lookup"><span data-stu-id="38912-129">See also</span></span>

- [<span data-ttu-id="38912-130">Модель криптографии</span><span class="sxs-lookup"><span data-stu-id="38912-130">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="38912-131">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="38912-131">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="38912-132">Кросс-платформенная криптография</span><span class="sxs-lookup"><span data-stu-id="38912-132">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="38912-133">Создание ключей для шифрования и расшифровки</span><span class="sxs-lookup"><span data-stu-id="38912-133">Generating keys for encryption and decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="38912-134">Шифрование данных</span><span class="sxs-lookup"><span data-stu-id="38912-134">Encrypting data</span></span>](encrypting-data.md)
- [<span data-ttu-id="38912-135">Расшифровка данных</span><span class="sxs-lookup"><span data-stu-id="38912-135">Decrypting data</span></span>](decrypting-data.md)
- [<span data-ttu-id="38912-136">ASP.NET Core Защита данных</span><span class="sxs-lookup"><span data-stu-id="38912-136">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)

---
title: Практическое руководство. Шифрование XML-элементов с помощью сертификатов X.509
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], X.509 certificates
- cryptography [.NET], X.509 certificates
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- System.Security.Cryptography.X509Certificate2 class
- X.509 certificates
- certificates, X.509 certificates
ms.assetid: 761f1c66-631c-47af-aa86-ad9c50cfa453
ms.openlocfilehash: a336997a8cb81f1838d9c5b1ec82bbb04326ed0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729334"
---
# <a name="how-to-encrypt-xml-elements-with-x509-certificates"></a><span data-ttu-id="43369-102">Практическое руководство. Шифрование XML-элементов с помощью сертификатов X.509</span><span class="sxs-lookup"><span data-stu-id="43369-102">How to: Encrypt XML Elements with X.509 Certificates</span></span>

<span data-ttu-id="43369-103">Классы можно использовать в пространстве имен <xref:System.Security.Cryptography.Xml> для шифрования элемента XML-документа.</span><span class="sxs-lookup"><span data-stu-id="43369-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt an element within an XML document.</span></span>  <span data-ttu-id="43369-104">Шифрование XML-данных — это стандартный способ обмена зашифрованными XML-данными и их хранения, позволяющий не беспокоиться о том, что эти данные могут быть прочитаны.</span><span class="sxs-lookup"><span data-stu-id="43369-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="43369-105">Дополнительные сведения о стандарте шифрования XML см. в спецификации консорциум W3C (W3C) для XML-шифрования, расположенного по адресу <https://www.w3.org/TR/xmldsig-core/> .</span><span class="sxs-lookup"><span data-stu-id="43369-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) specification for XML Encryption located at <https://www.w3.org/TR/xmldsig-core/>.</span></span>  
  
 <span data-ttu-id="43369-106">При помощи шифрования XML-данных можно заменить любой XML-элемент или документ элементом <`EncryptedData`>, содержащим зашифрованные XML-данные.</span><span class="sxs-lookup"><span data-stu-id="43369-106">You can use XML Encryption to replace any XML element or document with an <`EncryptedData`> element that contains the encrypted XML data.</span></span> <span data-ttu-id="43369-107">Элемент <`EncryptedData`> может включать в себя вложенные элементы, содержащие сведения о ключах и процессах, использованных при шифровании.</span><span class="sxs-lookup"><span data-stu-id="43369-107">The <`EncryptedData`> element can contain sub elements that include information about the keys and processes used during encryption.</span></span>  <span data-ttu-id="43369-108">Шифрование XML-данных позволяет документу содержать несколько зашифрованных элементов, а также позволяет шифровать элемент несколько раз.</span><span class="sxs-lookup"><span data-stu-id="43369-108">XML Encryption allows a document to contain multiple encrypted elements and allows an element to be encrypted multiple times.</span></span>  <span data-ttu-id="43369-109">В примере кода в данной процедуре показано создание элемента <`EncryptedData`> наряду с несколькими вложенными элементами, которые можно использовать позже при расшифровке.</span><span class="sxs-lookup"><span data-stu-id="43369-109">The code example in this procedure shows you how to create an <`EncryptedData`> element along with several other sub elements that you can use later during decryption.</span></span>  
  
<span data-ttu-id="43369-110">Этот пример выполняет шифрование XML-элемента с использованием двух ключей.</span><span class="sxs-lookup"><span data-stu-id="43369-110">This example encrypts an XML element using two keys.</span></span> <span data-ttu-id="43369-111">Пример программно извлекает сертификат и использует его для шифрования XML-элемента с помощью <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> метода.</span><span class="sxs-lookup"><span data-stu-id="43369-111">The example programmatically retrieves a certificate and uses it to encrypt an XML element using the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method.</span></span> <span data-ttu-id="43369-112">На внутреннем уровне метод <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> создает отдельный сеансовый ключ и использует его для шифрования XML-документа.</span><span class="sxs-lookup"><span data-stu-id="43369-112">Internally, the <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method creates a separate session key and uses it to encrypt the XML document.</span></span> <span data-ttu-id="43369-113">Этот метод шифрует сеансовый ключ и сохраняет его вместе с зашифрованным XML-элементом в новом элементе <`EncryptedData`>.</span><span class="sxs-lookup"><span data-stu-id="43369-113">This method encrypts the session key and saves it along with the encrypted XML within a new <`EncryptedData`> element.</span></span>  

<span data-ttu-id="43369-114">Чтобы расшифровать XML-элемент, вызовите <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> метод, который автоматически извлекает сертификат X. 509 из хранилища и выполняет необходимую расшифровку.</span><span class="sxs-lookup"><span data-stu-id="43369-114">To decrypt the XML element, call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method, which automatically retrieves the X.509 certificate from the store and performs the necessary decryption.</span></span>  <span data-ttu-id="43369-115">Дополнительные сведения о способах расшифровки XML-элемента, зашифрованного при использовании этой процедуры, см. в разделе [Практическое руководство. Расшифровка XML-элементов при помощи сертификатов X.509](how-to-decrypt-xml-elements-with-x-509-certificates.md).</span><span class="sxs-lookup"><span data-stu-id="43369-115">For more information about how to decrypt an XML element that was encrypted using this procedure, see [How to: Decrypt XML Elements with X.509 Certificates](how-to-decrypt-xml-elements-with-x-509-certificates.md).</span></span>  
  
<span data-ttu-id="43369-116">Этот пример подходит в ситуациях, когда нескольким приложениям нужен общий доступ к зашифрованным данным или когда приложению требуется сохранять зашифрованные данные между запусками.</span><span class="sxs-lookup"><span data-stu-id="43369-116">This example is appropriate for situations where multiple applications need to share encrypted data or where an application needs to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-encrypt-an-xml-element-with-an-x509-certificate"></a><span data-ttu-id="43369-117">Шифрование XML-элемента с использованием сертификата X.509</span><span class="sxs-lookup"><span data-stu-id="43369-117">To encrypt an XML element with an X.509 certificate</span></span>  

<span data-ttu-id="43369-118">Чтобы выполнить этот пример, необходимо создать тестовый сертификат и сохранить его в хранилище сертификатов.</span><span class="sxs-lookup"><span data-stu-id="43369-118">To run this example, you need to create a test certificate and save it in a certificate store.</span></span> <span data-ttu-id="43369-119">Инструкции для этой задачи предоставляются только для [средства создания сертификатов Windows (Makecert.exe)](/windows/desktop/SecCrypto/makecert).</span><span class="sxs-lookup"><span data-stu-id="43369-119">Instructions for that task are provided only for the Windows [Certificate Creation Tool (Makecert.exe)](/windows/desktop/SecCrypto/makecert).</span></span>

1. <span data-ttu-id="43369-120">Используйте [Makecert.exe](/windows/desktop/SecCrypto/makecert) , чтобы создать тестовый сертификат X. 509 и поместить его в локальное хранилище пользователей.</span><span class="sxs-lookup"><span data-stu-id="43369-120">Use [Makecert.exe](/windows/desktop/SecCrypto/makecert) to generate a test X.509 certificate and place it in the local user store.</span></span> <span data-ttu-id="43369-121">Необходимо создать ключ обмена и сделать его экспортируемым.</span><span class="sxs-lookup"><span data-stu-id="43369-121">You must generate an exchange key and you must make the key exportable.</span></span> <span data-ttu-id="43369-122">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="43369-122">Run the following command:</span></span>  
  
    ```console  
    makecert -r -pe -n "CN=XML_ENC_TEST_CERT" -b 01/01/2020 -e 01/01/2025 -sky exchange -ss my  
    ```  
  
2. <span data-ttu-id="43369-123">Создайте объект <xref:System.Security.Cryptography.X509Certificates.X509Store> и инициализируйте его, чтобы открыть хранилище текущего пользователя.</span><span class="sxs-lookup"><span data-stu-id="43369-123">Create an <xref:System.Security.Cryptography.X509Certificates.X509Store> object and initialize it to open the current user store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#2)]
     [!code-vb[HowToEncryptXMLElementX509#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#2)]  
  
3. <span data-ttu-id="43369-124">Откройте хранилище в режиме только для чтения.</span><span class="sxs-lookup"><span data-stu-id="43369-124">Open the store in read-only mode.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#3)]
     [!code-vb[HowToEncryptXMLElementX509#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#3)]  
  
4. <span data-ttu-id="43369-125">Инициализируйте <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> всеми сертификатами в хранилище.</span><span class="sxs-lookup"><span data-stu-id="43369-125">Initialize an <xref:System.Security.Cryptography.X509Certificates.X509Certificate2Collection> with all of the certificates in the store.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#4)]
     [!code-vb[HowToEncryptXMLElementX509#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#4)]  
  
5. <span data-ttu-id="43369-126">Выполните перечисление сертификатов в хранилище, чтобы найти сертификат с соответствующим именем.</span><span class="sxs-lookup"><span data-stu-id="43369-126">Enumerate through the certificates in the store and find the certificate with the appropriate name.</span></span>  <span data-ttu-id="43369-127">В этом примере сертификат имеет имя `"CN=XML_ENC_TEST_CERT"`.</span><span class="sxs-lookup"><span data-stu-id="43369-127">In this example, the certificate is named `"CN=XML_ENC_TEST_CERT"`.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#5)]
     [!code-vb[HowToEncryptXMLElementX509#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#5)]  
  
6. <span data-ttu-id="43369-128">Закройте хранилище после нахождения сертификата.</span><span class="sxs-lookup"><span data-stu-id="43369-128">Close the store after the certificate is located.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#6)]
     [!code-vb[HowToEncryptXMLElementX509#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#6)]  
  
7. <span data-ttu-id="43369-129">Создайте объект <xref:System.Xml.XmlDocument>, загрузив XML-файл с диска.</span><span class="sxs-lookup"><span data-stu-id="43369-129">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="43369-130">Объект <xref:System.Xml.XmlDocument> содержит XML-элемент для шифрования.</span><span class="sxs-lookup"><span data-stu-id="43369-130">The <xref:System.Xml.XmlDocument> object contains the XML element to encrypt.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#7)]
     [!code-vb[HowToEncryptXMLElementX509#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#7)]  
  
8. <span data-ttu-id="43369-131">Найдите указанный элемент в объекте <xref:System.Xml.XmlDocument> и создайте новый объект <xref:System.Xml.XmlElement> для представления того элемента, который требуется зашифровать.</span><span class="sxs-lookup"><span data-stu-id="43369-131">Find the specified element in the <xref:System.Xml.XmlDocument> object and create a new <xref:System.Xml.XmlElement> object to represent the element you want to encrypt.</span></span>  <span data-ttu-id="43369-132">В этом примере выполняется шифрование элемента `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="43369-132">In this example, the `"creditcard"` element is encrypted.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#8)]
     [!code-vb[HowToEncryptXMLElementX509#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#8)]  
  
9. <span data-ttu-id="43369-133">Создайте новый экземпляр класса <xref:System.Security.Cryptography.Xml.EncryptedXml> и используйте его для шифрования указанного элемента при помощи сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="43369-133">Create a new instance of the <xref:System.Security.Cryptography.Xml.EncryptedXml> class and use it to encrypt the specified element using the X.509 certificate.</span></span>  <span data-ttu-id="43369-134">Метод <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> возвращает зашифрованный элемент в виде объекта <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="43369-134">The <xref:System.Security.Cryptography.Xml.EncryptedXml.Encrypt%2A> method returns the encrypted element as an <xref:System.Security.Cryptography.Xml.EncryptedData> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#9)]
     [!code-vb[HowToEncryptXMLElementX509#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#9)]  
  
10. <span data-ttu-id="43369-135">Замените элемент из исходного объекта <xref:System.Xml.XmlDocument> на элемент <xref:System.Security.Cryptography.Xml.EncryptedData>.</span><span class="sxs-lookup"><span data-stu-id="43369-135">Replace the element from the original <xref:System.Xml.XmlDocument> object with the <xref:System.Security.Cryptography.Xml.EncryptedData> element.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#10)]
     [!code-vb[HowToEncryptXMLElementX509#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#10)]  
  
11. <span data-ttu-id="43369-136">Сохраните объект <xref:System.Xml.XmlDocument>.</span><span class="sxs-lookup"><span data-stu-id="43369-136">Save the <xref:System.Xml.XmlDocument> object.</span></span>  
  
     [!code-csharp[HowToEncryptXMLElementX509#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#11)]
     [!code-vb[HowToEncryptXMLElementX509#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#11)]  
  
## <a name="example"></a><span data-ttu-id="43369-137">Пример</span><span class="sxs-lookup"><span data-stu-id="43369-137">Example</span></span>  

 <span data-ttu-id="43369-138">В этом примере предполагается, что файл с именем `"test.xml"` существует в том же каталоге, что и скомпилированная программа.</span><span class="sxs-lookup"><span data-stu-id="43369-138">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="43369-139">Кроме того, предполагается, что `"test.xml"` содержит элемент `"creditcard"`.</span><span class="sxs-lookup"><span data-stu-id="43369-139">It also assumes that `"test.xml"` contains a `"creditcard"` element.</span></span>  <span data-ttu-id="43369-140">Можно поместить следующий XML-код в файл с именем `test.xml` и использовать его вместе с данным примером.</span><span class="sxs-lookup"><span data-stu-id="43369-140">You can place the following XML into a file called `test.xml` and use it with this example.</span></span>  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToEncryptXMLElementX509#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToEncryptXMLElementX509/cs/sample.cs#1)]
 [!code-vb[HowToEncryptXMLElementX509#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToEncryptXMLElementX509/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="43369-141">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="43369-141">Compiling the Code</span></span>  
  
- <span data-ttu-id="43369-142">В проекте, предназначенном для .NET Framework, включите ссылку на `System.Security.dll` .</span><span class="sxs-lookup"><span data-stu-id="43369-142">In a project that targets .NET Framework, include a reference to `System.Security.dll`.</span></span>

- <span data-ttu-id="43369-143">В проекте, ориентированном на .NET Core или .NET 5, установите пакет NuGet [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span><span class="sxs-lookup"><span data-stu-id="43369-143">In a project that targets .NET Core or .NET 5, install NuGet package [System.Security.Cryptography.Xml](https://www.nuget.org/packages/System.Security.Cryptography.Xml).</span></span>
  
- <span data-ttu-id="43369-144">Включите следующие пространства имен: <xref:System.Xml>, <xref:System.Security.Cryptography> и <xref:System.Security.Cryptography.Xml>.</span><span class="sxs-lookup"><span data-stu-id="43369-144">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="43369-145">Безопасность .NET</span><span class="sxs-lookup"><span data-stu-id="43369-145">.NET Security</span></span>
  
<span data-ttu-id="43369-146">Используемый в этом примере сертификат X.509 предназначен исключительно для тестирования.</span><span class="sxs-lookup"><span data-stu-id="43369-146">The X.509 certificate used in this example is for test purposes only.</span></span>  <span data-ttu-id="43369-147">Приложения должны использовать сертификат X. 509, созданный доверенным центром сертификации.</span><span class="sxs-lookup"><span data-stu-id="43369-147">Applications should use an X.509 certificate generated by a trusted certificate authority.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43369-148">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="43369-148">See also</span></span>

- [<span data-ttu-id="43369-149">Модель криптографии</span><span class="sxs-lookup"><span data-stu-id="43369-149">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="43369-150">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="43369-150">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="43369-151">Кросс-платформенная криптография</span><span class="sxs-lookup"><span data-stu-id="43369-151">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="43369-152">Практическое руководство. Дешифровка XML-элементов с помощью сертификатов X.509</span><span class="sxs-lookup"><span data-stu-id="43369-152">How to: Decrypt XML Elements with X.509 Certificates</span></span>](how-to-decrypt-xml-elements-with-x-509-certificates.md)
- [<span data-ttu-id="43369-153">ASP.NET Core Защита данных</span><span class="sxs-lookup"><span data-stu-id="43369-153">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)

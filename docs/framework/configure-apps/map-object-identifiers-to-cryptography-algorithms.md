---
title: Отображение идентификаторов объектов на криптографические алгоритмы
description: См. раздел как сопоставлять идентификатор объекта (OID) с алгоритмом шифрования в .NET с помощью элементов Оидентри и элементе nameentry в XML-файле конфигурации.
ms.date: 03/30/2017
helpviewer_keywords:
- digital signatures
- identifiers, mapping object identifiers
- cryptographic algorithms
- mapping object identifiers
- cryptography, mapping object identifiers
ms.assetid: c9673f81-bf9e-47fd-bc6f-6bc1c1c4c15e
ms.openlocfilehash: 5416ddbb766dfde56fa28a3853ed448cc73f25a2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189387"
---
# <a name="mapping-object-identifiers-to-cryptography-algorithms"></a><span data-ttu-id="99548-103">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="99548-103">Mapping Object Identifiers to Cryptography Algorithms</span></span>

<span data-ttu-id="99548-104">Цифровые подписи гарантируют, что данные не были изменены при отправке из одной программы в другую.</span><span class="sxs-lookup"><span data-stu-id="99548-104">Digital signatures ensure that data is not tampered with when it is sent from one program to another.</span></span> <span data-ttu-id="99548-105">Обычно цифровая подпись вычислена путем применения математической функции к хэшу подписываемых данных.</span><span class="sxs-lookup"><span data-stu-id="99548-105">Typically the digital signature is computed by applying a mathematical function to the hash of the data to be signed.</span></span> <span data-ttu-id="99548-106">При форматировании хэш-значения для подписи некоторые алгоритмы цифровых подписей добавляют в операцию форматирования идентификатор объекта ASN. 1 (OID).</span><span class="sxs-lookup"><span data-stu-id="99548-106">When formatting a hash value to be signed, some digital signature algorithms append an ASN.1 Object Identifier (OID) as part of the formatting operation.</span></span> <span data-ttu-id="99548-107">OID определяет алгоритм, который использовался для вычисления хэша.</span><span class="sxs-lookup"><span data-stu-id="99548-107">The OID identifies the algorithm that was used to compute the hash.</span></span> <span data-ttu-id="99548-108">Вы можете сопоставлять алгоритмы с идентификаторами объектов, чтобы расширить механизм криптографии для использования пользовательских алгоритмов.</span><span class="sxs-lookup"><span data-stu-id="99548-108">You can map algorithms to object identifiers to extend the cryptography mechanism to use custom algorithms.</span></span> <span data-ttu-id="99548-109">В следующем примере показано, как сопоставлять идентификатор объекта с новым алгоритмом хэширования.</span><span class="sxs-lookup"><span data-stu-id="99548-109">The following example shows how to map an object identifier to a new hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MyNewHash="MyNewHashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="NewHash" class="MyNewHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.14.33.42.46"  name="NewHash"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="99548-110">[ \<oidEntry> Элемент](./file-schema/cryptography/oidentry-element.md) содержит два атрибута.</span><span class="sxs-lookup"><span data-stu-id="99548-110">The [\<oidEntry> element](./file-schema/cryptography/oidentry-element.md) contains two attributes.</span></span> <span data-ttu-id="99548-111">Атрибут **OID** — это номер идентификатора объекта.</span><span class="sxs-lookup"><span data-stu-id="99548-111">The **OID** attribute is the object identifier number.</span></span> <span data-ttu-id="99548-112">Атрибут **Name** — это значение атрибута **Name** из [ \<nameEntry> элемента](./file-schema/cryptography/nameentry-element.md).</span><span class="sxs-lookup"><span data-stu-id="99548-112">The **name** attribute is the value of the **name** attribute from the [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md).</span></span> <span data-ttu-id="99548-113">Необходимо сопоставить имя алгоритма с классом, чтобы идентификатор объекта можно было сопоставить с простым именем.</span><span class="sxs-lookup"><span data-stu-id="99548-113">There must be a mapping from an algorithm name to a class before an object identifier can be mapped to a simple name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99548-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="99548-114">See also</span></span>

- [<span data-ttu-id="99548-115">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="99548-115">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
- [<span data-ttu-id="99548-116">службы шифрования</span><span class="sxs-lookup"><span data-stu-id="99548-116">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)

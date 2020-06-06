---
title: Настройка криптографических классов
ms.date: 03/30/2017
helpviewer_keywords:
- configuration files [.NET Framework], cryptography
- cryptographic algorithms
- security [.NET Framework], encryption
- cryptography, classes
- .NET Framework application configuration, cryptography
- default cryptography
ms.assetid: eee3ccb8-2c0d-4f35-b38d-6892a46c14e5
ms.openlocfilehash: e53f4c5c9e24fb25b43b7f27b80ab984214eeac2
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/06/2020
ms.locfileid: "69927772"
---
# <a name="configuring-cryptography-classes"></a><span data-ttu-id="27271-102">Настройка криптографических классов</span><span class="sxs-lookup"><span data-stu-id="27271-102">Configuring Cryptography Classes</span></span>
<span data-ttu-id="27271-103">Windows SDK позволяет администраторам компьютеров настраивать алгоритмы шифрования по умолчанию и реализации алгоритмов, используемые .NET Framework и соответствующим образом написанными приложениями.</span><span class="sxs-lookup"><span data-stu-id="27271-103">The Windows SDK allows computer administrators to configure the default cryptographic algorithms and algorithm implementations that the .NET Framework and appropriately written applications use.</span></span>  <span data-ttu-id="27271-104">Например, предприятие с собственной реализацией алгоритма шифрования может сделать реализацию по умолчанию вместо реализации, поставляемой в Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="27271-104">For example, an enterprise that has its own implementation of a cryptographic algorithm can make that implementation the default instead of the implementation shipped in the Windows SDK.</span></span> <span data-ttu-id="27271-105">Несмотря на то, что управляемые приложения, использующие шифрование, всегда могут явно привязываться к определенной реализации, рекомендуется создавать криптографические объекты с помощью системы конфигурации шифрования.</span><span class="sxs-lookup"><span data-stu-id="27271-105">Although managed applications that use cryptography can always choose to explicitly bind to a particular implementation, it is recommended that they create cryptographic objects by using the crypto configuration system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27271-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="27271-106">In This Section</span></span>  
 [<span data-ttu-id="27271-107">Отображение имен алгоритмов на криптографические классы</span><span class="sxs-lookup"><span data-stu-id="27271-107">Mapping Algorithm Names to Cryptography Classes</span></span>](map-algorithm-names-to-cryptography-classes.md)  
 <span data-ttu-id="27271-108">Описывает, как сопоставлять имя алгоритма с криптографическим классом.</span><span class="sxs-lookup"><span data-stu-id="27271-108">Describes how to map an algorithm name to a cryptography class.</span></span>  
  
 [<span data-ttu-id="27271-109">Отображение идентификаторов объектов на криптографические алгоритмы</span><span class="sxs-lookup"><span data-stu-id="27271-109">Mapping Object Identifiers to Cryptography Algorithms</span></span>](map-object-identifiers-to-cryptography-algorithms.md)  
 <span data-ttu-id="27271-110">Описывает, как сопоставлять идентификатор объекта с алгоритмом шифрования.</span><span class="sxs-lookup"><span data-stu-id="27271-110">Describes how to map an object identifier to a cryptography algorithm.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="27271-111">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="27271-111">Related Sections</span></span>  
 [<span data-ttu-id="27271-112">Службы шифрования</span><span class="sxs-lookup"><span data-stu-id="27271-112">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)  
 <span data-ttu-id="27271-113">Содержит общие сведения о службах шифрования, предоставляемых Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="27271-113">Provides an overview of cryptographic services provided by the Windows SDK.</span></span>  
  
 [<span data-ttu-id="27271-114">Схема параметров криптографии</span><span class="sxs-lookup"><span data-stu-id="27271-114">Cryptography Settings Schema</span></span>](./file-schema/cryptography/index.md)  
 <span data-ttu-id="27271-115">Описание элементов, с помощью которых можно сопоставить понятные имена алгоритмов с классами, реализующими алгоритмы шифрования.</span><span class="sxs-lookup"><span data-stu-id="27271-115">Describes elements that map friendly algorithm names to classes that implement cryptography algorithms.</span></span>

---
title: Модель шифрования .NET
description: Ознакомьтесь с реализациями обычных криптографических алгоритмов в .NET. Изучение расширяемой криптографической модели наследования объектов, проектирования потоков & конфигурации.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cryptography [.NET], model
- encryption [.NET], model
ms.assetid: 12fecad4-fbab-432a-bade-2f05976a2971
ms.openlocfilehash: 0b3e07238bf0932572c222f7b947cfa7ae0221a9
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556999"
---
# <a name="net-cryptography-model"></a>Модель шифрования .NET

.NET предоставляет реализации многих стандартных криптографических алгоритмов, и модель шифрования .NET является расширяемой.

## <a name="object-inheritance"></a>Наследование объектов

Система криптографии .NET реализует расширяемый шаблон наследования производного класса. Иерархия имеет представленный ниже вид.

- Класс типа алгоритма, например <xref:System.Security.Cryptography.SymmetricAlgorithm> , <xref:System.Security.Cryptography.AsymmetricAlgorithm> или <xref:System.Security.Cryptography.HashAlgorithm> . Этот уровень является абстрактным.

- Класс алгоритма, наследующий от класса типа алгоритма, например <xref:System.Security.Cryptography.Aes>, <xref:System.Security.Cryptography.RSA> или <xref:System.Security.Cryptography.ECDiffieHellman>. Этот уровень является абстрактным.

- Реализация класса алгоритма, наследующего от класса алгоритма, например <xref:System.Security.Cryptography.AesManaged>, <xref:System.Security.Cryptography.RC2CryptoServiceProvider> или <xref:System.Security.Cryptography.ECDiffieHellmanCng>. Этот уровень полностью реализован.

Этот шаблон производных классов позволяет добавить новый алгоритм или новую реализацию существующего алгоритма. Например, чтобы создать новый алгоритм открытого ключа, можно наследовать от класса <xref:System.Security.Cryptography.AsymmetricAlgorithm>. Чтобы создать новую реализацию определенного алгоритма, можно создать неабстрактный производный класс этого алгоритма.

## <a name="how-algorithms-are-implemented-in-net"></a>Реализация алгоритмов в .NET

В качестве примера различных реализаций, доступных для алгоритма, рассмотрим симметричные алгоритмы. Основой для всех симметричных алгоритмов является <xref:System.Security.Cryptography.SymmetricAlgorithm> , которая наследуется <xref:System.Security.Cryptography.Aes> , <xref:System.Security.Cryptography.TripleDES> и другие, которые больше не рекомендуются.

<xref:System.Security.Cryptography.Aes>наследуется <xref:System.Security.Cryptography.AesCryptoServiceProvider> , <xref:System.Security.Cryptography.AesCng> и <xref:System.Security.Cryptography.AesManaged> .

В .NET Framework в Windows:

* `*CryptoServiceProvider`классы алгоритмов, такие как <xref:System.Security.Cryptography.AesCryptoServiceProvider> , являются оболочками для реализации алгоритма с помощью API шифрования Windows (CAPI).
* `*Cng`классы алгоритмов, такие как, <xref:System.Security.Cryptography.ECDiffieHellmanCng> являются оболочками для реализации Windows криптографии следующего поколения (CNG).
* `*Managed`классы, такие как <xref:System.Security.Cryptography.AesManaged> , полностью записываются в управляемом коде. `*Managed`реализации не сертифицированы Федеральным стандартом обработки информации (FIPS) и могут быть медленнее, чем `*CryptoServiceProvider` классы- `*Cng` оболочки.

В .NET Core и .NET 5 и более поздних версиях все классы реализации ( `*CryptoServiceProvider` , `*Managed` и `*Cng` ) являются оболочками для алгоритмов операционной системы (ОС). Если алгоритмы ОС сертифицированы по стандарту FIPS, .NET использует алгоритмы, сертифицированные FIPS. Дополнительные сведения см. в статье [кросс-платформенное шифрование](cross-platform-cryptography.md).

В большинстве случаев нет необходимости напрямую ссылаться на класс реализации алгоритма, например `AesCryptoServiceProvider` . Обычно нужные методы и свойства находятся в классе базового алгоритма, например `Aes` . Создайте экземпляр класса реализации по умолчанию, используя фабричный метод в классе базового алгоритма и обратитесь к классу базового алгоритма. Например, см. выделенную строку кода в следующем примере:

:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs" highlight="16":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb" highlight="12":::

## <a name="cryptographic-configuration"></a>Криптографическая конфигурация

Конфигурация криптографии позволяет разрешать определенную реализацию алгоритма в имя алгоритма, обеспечивая расширяемость классов шифрования .NET. Вы можете добавить свою собственную аппаратную или программную реализацию алгоритма и сопоставить ее с необходимым именем алгоритма. Если алгоритм не задан в файле конфигурации, используются параметры по умолчанию.

## <a name="choosing-an-algorithm"></a>Выбор алгоритма

Алгоритм можно выбирать, исходя из различных причин, например для обеспечения целостности данных, для обеспечения конфиденциальности данных или для создания ключа. Симметричные и хэш-алгоритмы предназначены для защиты данных от нарушения целостности (защита от изменения) или конфиденциальности (защита от просмотра). Хэш-алгоритмы используются в основном для обеспечения целостности данных.

Ниже приведен список рекомендуемых алгоритмов в зависимости от приложения.

- Конфиденциальность данных:
  - <xref:System.Security.Cryptography.Aes>
- Целостность данных:
  - <xref:System.Security.Cryptography.HMACSHA256>
  - <xref:System.Security.Cryptography.HMACSHA512>
- Цифровая подпись:
  - <xref:System.Security.Cryptography.ECDsa>
  - <xref:System.Security.Cryptography.RSA>
- Обмен ключами:
  - <xref:System.Security.Cryptography.ECDiffieHellman>
  - <xref:System.Security.Cryptography.RSA>
- Генерация случайных чисел:
  - <xref:System.Security.Cryptography.RandomNumberGenerator.Create%2A?displayProperty=nameWithType>
- Формирование ключа из пароля:
  - <xref:System.Security.Cryptography.Rfc2898DeriveBytes>

## <a name="see-also"></a>См. также раздел

- [службы шифрования](cryptographic-services.md)
- [Кросс-платформенная криптография](cross-platform-cryptography.md)
- [ASP.NET Core Защита данных](/aspnet/core/security/data-protection/introduction)

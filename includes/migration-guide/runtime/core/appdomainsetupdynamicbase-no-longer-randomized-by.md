---
ms.openlocfilehash: 08ad6fd4ccb6d5ddbbb4fa7ef1b325ce30689748
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621414"
---
### <a name="appdomainsetupdynamicbase-is-no-longer-randomized-by-userandomizedstringhashalgorithm"></a>AppDomainSetup.DynamicBase больше не задается случайно с помощью UseRandomizedStringHashAlgorithm

#### <a name="details"></a>Подробнее

В версиях до .NET Framework 4.6 значение <xref:System.AppDomainSetup.DynamicBase> задавалось случайным образом между доменами приложений или между процессами, если в файле конфигурации приложения был включен UseRandomizedStringHashAlgorithm. Начиная с версии .NET Framework 4.6, <xref:System.AppDomainSetup.DynamicBase> будет возвращать постоянный результат между различными выполняющимися экземплярами приложения и между различными доменами приложений. Динамические основания при этом по-прежнему будут различаться для разных приложений. Это изменение исключает только случайный элемент именования для различных экземпляров одного приложения.

#### <a name="suggestion"></a>Предложение

Обратите внимание, что включение <code>UseRandomizedStringHashAlgorithm</code> не приведет к случайной установке <xref:System.AppDomainSetup.DynamicBase>. Если требуется случайное основание, для его получения необходимо использовать код приложения, а не этот API.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.6|
|Type|Среда выполнения

#### <a name="affected-apis"></a>Затронутые API

-<xref:System.AppDomainSetup.DynamicBase?displayProperty=nameWithType></li></ul>|

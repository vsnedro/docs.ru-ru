---
title: Порядок модульных тестов
description: Сведения о том, как упорядочить модульные тесты в .NET Core.
author: IEvangelist
ms.author: dapine
ms.date: 05/18/2020
zone_pivot_groups: unit-testing-framework-set-one
ms.openlocfilehash: a7b6b66e4cc865d4ec6b7cfc31ac79767935df2f
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506387"
---
# <a name="order-unit-tests"></a>Порядок модульных тестов

Иногда нужно выполнять модульные тесты в определенном порядке. В идеальном случае порядок выполнения модульных тестов _не должен_ иметь значение. Мы [настоятельно рекомендуем](unit-testing-best-practices.md) отказаться от упорядочивания модульных тестов. Но иногда без этого невозможно обойтись. Если вы столкнулись с такой ситуацией, эта статья поможет вам упорядочить выполнение тестов.

Если вы предпочитаете изучать исходный код, воспользуйтесь репозиторием примеров [с упорядочением модульных тестов в .NET Core](/samples/dotnet/samples/order-unit-tests-cs).

> [!TIP]
> Помимо возможностей для упорядочения, которые описаны в этой статье, можно [создать пользовательские списков воспроизведения в Visual Studio](/visualstudio/test/run-unit-tests-with-test-explorer?view=vs-2019#create-custom-playlists).

:::zone pivot="mstest"

## <a name="order-alphabetically"></a>Упорядочение по алфавиту

В MSTest тесты автоматически упорядочиваются по именам.

> [!NOTE]
> Тест с именем `Test14` всегда будет выполняться раньше `Test2`, хотя числовое значение `2` меньше `14`. Это связано с тем, что для упорядочения используются текстовые значения имен тестов.

:::code language="csharp" source="snippets/order-unit-tests/csharp/MSTest.Project/ByAlphabeticalOrder.cs":::

:::zone-end
:::zone pivot="xunit"

Платформа тестирования xUnit предоставляет больше возможностей, а также более высокую точность и уровень контроля порядка выполнения тестов. Для управления порядком выполнения тестовых случаев в классе следует реализовать интерфейсы `ITestCaseOrderer` и `ITestCollectionOrderer` (коллекции тестов).

## <a name="order-by-test-case-alphabetically"></a>Упорядочение тестовых случае по алфавиту

Чтобы упорядочить тестовые случаи по имени метода, следует реализовать `ITestCaseOrderer` и предоставить механизм упорядочения.

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/Orderers/AlphabeticalOrderer.cs":::

Затем задайте порядок тестовых случаев в тестовом классе с помощью `TestCaseOrdererAttribute`.

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/ByAlphabeticalOrder.cs":::

## <a name="order-by-collection-alphabetically"></a>Упорядочение коллекций по алфавиту

Чтобы упорядочить коллекции по отображаемому имени, следует реализовать `ITestCollectionOrderer` и предоставить механизм упорядочения.

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/Orderers/DisplayNameOrderer.cs":::

Так как коллекции тестов могут выполняться параллельно, явным образом отключите параллелизацию тестов для коллекций с помощью `CollectionBehaviorAttribute`. Затем укажите реализацию в `TestCollectionOrdererAttribute`.

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/ByDisplayName.cs":::

## <a name="order-by-custom-attribute"></a>Упорядочение по настраиваемому атрибуту

Чтобы упорядочить тесты xUnit по пользовательским атрибутам, прежде всего нужно создать для этого атрибут. Определите `TestPriorityAttribute` следующим образом:

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/Attributes/TestPriorityAttribute.cs":::

Далее мы рассмотрим реализацию `PriorityOrderer` интерфейса `ITestCaseOrderer`.

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/Orderers/PriorityOrderer.cs":::

Затем задайте порядок тестовых случаев в тестовом классе с помощью `TestCaseOrdererAttribute` для `PriorityOrderer`.

:::code language="csharp" source="snippets/order-unit-tests/csharp/XUnit.TestProject/ByPriorityOrder.cs":::

:::zone-end
:::zone pivot="nunit"

## <a name="order-by-priority"></a>Упорядочение по приоритету

Чтобы явным образом упорядочить тесты, в NUnit можно использовать [`OrderAttribute`](https://github.com/nunit/docs/wiki/Order-Attribute). Тесты с этим атрибутом всегда выполняются раньше, чем остальные. Для определения порядка выполнения модульных тестов используется значение order.

:::code language="csharp" source="snippets/order-unit-tests/csharp/NUnit.TestProject/ByOrder.cs":::

:::zone-end

## <a name="next-steps"></a>Следующие шаги

> [!div class="nextstepaction"]
> [Объем протестированного кода — модульный тест](unit-testing-code-coverage.md)

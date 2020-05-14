---
title: Флаги компонентов
description: Реализация флагов функций в собственных облачных приложениях с использованием конфигурации приложения Azure
ms.date: 05/03/2020
ms.openlocfilehash: 72e1bfe777854a74fcac926811caf97e59986146
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "83398323"
---
# <a name="feature-flags"></a><span data-ttu-id="50f68-103">Флаги компонентов</span><span class="sxs-lookup"><span data-stu-id="50f68-103">Feature flags</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="50f68-104">В главе 1 мы подтверждаем, что облачная машинная поддержка очень важна для ускорения и гибкости.</span><span class="sxs-lookup"><span data-stu-id="50f68-104">In chapter 1, we affirmed that cloud native is much about speed and agility.</span></span> <span data-ttu-id="50f68-105">Пользователи предполагают быстрое реагирование, инновационные функции и нулевое время простоя.</span><span class="sxs-lookup"><span data-stu-id="50f68-105">Users expect rapid responsiveness, innovative features, and zero downtime.</span></span> <span data-ttu-id="50f68-106">`Feature flags`— Это современный метод развертывания, который помогает повысить гибкость облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="50f68-106">`Feature flags` are a modern deployment technique that helps increase agility for cloud-native applications.</span></span> <span data-ttu-id="50f68-107">Они позволяют развертывать новые функции в рабочей среде, но ограничивать их доступность.</span><span class="sxs-lookup"><span data-stu-id="50f68-107">They enable you to deploy new features into a production environment, but restrict their availability.</span></span> <span data-ttu-id="50f68-108">С помощью жеста коммутатора можно активировать новую функцию для конкретных пользователей без перезапуска приложения или развертывания нового кода.</span><span class="sxs-lookup"><span data-stu-id="50f68-108">With the flick of a switch, you can activate a new feature for specific users without restarting the app or deploying new code.</span></span> <span data-ttu-id="50f68-109">Они отделяют выпуск новых функций от развертывания кода.</span><span class="sxs-lookup"><span data-stu-id="50f68-109">They separate the release of new features from their code deployment.</span></span>

<span data-ttu-id="50f68-110">Флаги функций создаются на основе условной логики, которая контролирует видимость функций для пользователей во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="50f68-110">Feature flags are built upon conditional logic that control visibility of functionality for users at runtime.</span></span> <span data-ttu-id="50f68-111">В современных облачных системах часто развертывать новые функции в рабочей среде, но тестировать их с ограниченной аудиторией.</span><span class="sxs-lookup"><span data-stu-id="50f68-111">In modern cloud-native systems, it's common to deploy new features into production early, but test them with a limited audience.</span></span> <span data-ttu-id="50f68-112">По мере роста уверенности функция может быть постепенно сведена к более широкой аудитории.</span><span class="sxs-lookup"><span data-stu-id="50f68-112">As confidence increases, the feature can be incrementally rolled out to wider audiences.</span></span>

<span data-ttu-id="50f68-113">Ниже приведены другие варианты использования флагов компонентов.</span><span class="sxs-lookup"><span data-stu-id="50f68-113">Other use cases for feature flags include:</span></span>

- <span data-ttu-id="50f68-114">Ограничьте функциональные возможности уровня "Премиум" конкретными группами клиентов, которые хотят платить более высокие платежи по подписке.</span><span class="sxs-lookup"><span data-stu-id="50f68-114">Restrict premium functionality to specific customer groups willing to pay higher subscription fees.</span></span>
- <span data-ttu-id="50f68-115">Стабилизация системы за счет быстрой деактивации функции, которая позволяет избежать риска отката или немедленного исправления.</span><span class="sxs-lookup"><span data-stu-id="50f68-115">Stabilize a system by quickly deactivating a problem feature, avoiding the risks of a rollback or immediate hotfix.</span></span>
- <span data-ttu-id="50f68-116">Отключите дополнительную функцию с высоким потреблением ресурсов во время пиковых периодов использования.</span><span class="sxs-lookup"><span data-stu-id="50f68-116">Disable an optional feature with high resource consumption during peak usage periods.</span></span>
- <span data-ttu-id="50f68-117">Проведите `experimental feature releases` до небольших сегментов пользователей, чтобы проверить возможность и популярность.</span><span class="sxs-lookup"><span data-stu-id="50f68-117">Conduct `experimental feature releases` to small user segments to validate feasibility and popularity.</span></span>

<span data-ttu-id="50f68-118">Флаги функций также доразвивают `trunk-based` разработку.</span><span class="sxs-lookup"><span data-stu-id="50f68-118">Feature flags also promote `trunk-based` development.</span></span> <span data-ttu-id="50f68-119">Это модель ветвления системы управления версиями, в которой разработчики совместно работают над функциями в одной ветви.</span><span class="sxs-lookup"><span data-stu-id="50f68-119">It's a source-control branching model where developers collaborate on features in a single branch.</span></span> <span data-ttu-id="50f68-120">Этот подход позволяет снизить риск и сложность объединения большого числа длительно выполняемых ветвей компонентов.</span><span class="sxs-lookup"><span data-stu-id="50f68-120">The approach minimizes the risk and complexity of merging large numbers of long-running feature branches.</span></span> <span data-ttu-id="50f68-121">Функции недоступны до тех пор, пока не будут активированы.</span><span class="sxs-lookup"><span data-stu-id="50f68-121">Features are unavailable until activated.</span></span>

## <a name="implementing-feature-flags"></a><span data-ttu-id="50f68-122">Реализация флагов функций</span><span class="sxs-lookup"><span data-stu-id="50f68-122">Implementing feature flags</span></span>

<span data-ttu-id="50f68-123">По сути, флаг функции является ссылкой на простой `decision object` .</span><span class="sxs-lookup"><span data-stu-id="50f68-123">At its core, a feature flag is a reference to a simple `decision object`.</span></span> <span data-ttu-id="50f68-124">Он возвращает логическое состояние `on` или `off` .</span><span class="sxs-lookup"><span data-stu-id="50f68-124">It returns a Boolean state of `on` or `off`.</span></span> <span data-ttu-id="50f68-125">Флаг обычно заключает в оболочку блок кода, который инкапсулирует возможность функции.</span><span class="sxs-lookup"><span data-stu-id="50f68-125">The flag typically wraps a block of code that encapsulates a feature capability.</span></span> <span data-ttu-id="50f68-126">Состояние флага определяет, выполняется ли этот блок кода для данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="50f68-126">The state of the flag determines whether that code block executes for a given user.</span></span> <span data-ttu-id="50f68-127">На рис. 10-11 показана реализация.</span><span class="sxs-lookup"><span data-stu-id="50f68-127">Figure 10-11 shows the implementation.</span></span>

```c#
if (featureFlag) {
    // Run this code block if the featureFlag value is true
} else {
    // Run this code block if the featureFlag value is false
}
```

<span data-ttu-id="50f68-128">**Рис. 10-11** -простая реализация флага функции.</span><span class="sxs-lookup"><span data-stu-id="50f68-128">**Figure 10-11** - Simple feature flag implementation.</span></span>

<span data-ttu-id="50f68-129">Обратите внимание, что этот подход отделяет логику принятия решений от кода функции.</span><span class="sxs-lookup"><span data-stu-id="50f68-129">Note how this approach separates the decision logic from the feature code.</span></span>

<span data-ttu-id="50f68-130">В главе 1 мы обсуждали `Twelve-Factor App` .</span><span class="sxs-lookup"><span data-stu-id="50f68-130">In chapter 1, we discussed the `Twelve-Factor App`.</span></span> <span data-ttu-id="50f68-131">Рекомендуется хранить параметры конфигурации, которые являются внешними по отношению к исполняемому коду приложения.</span><span class="sxs-lookup"><span data-stu-id="50f68-131">The guidance recommended keeping configuration settings external from application executable code.</span></span> <span data-ttu-id="50f68-132">При необходимости параметры можно считывать из внешнего источника.</span><span class="sxs-lookup"><span data-stu-id="50f68-132">When needed, settings can be read in from the external source.</span></span> <span data-ttu-id="50f68-133">Значения конфигурации флагов компонентов также должны быть независимыми от своей базы кода.</span><span class="sxs-lookup"><span data-stu-id="50f68-133">Feature flag configuration values should also be independent from their codebase.</span></span> <span data-ttu-id="50f68-134">По конфигурации флага выведения в отдельном репозитории можно изменить состояние флага без изменения и повторного развертывания приложения.</span><span class="sxs-lookup"><span data-stu-id="50f68-134">By externalizing flag configuration in a separate repository, you can change flag state without modifying and redeploying the application.</span></span>

<span data-ttu-id="50f68-135">[Конфигурация приложений Azure](https://docs.microsoft.com/azure/azure-app-configuration/overview) предоставляет централизованный репозиторий для флагов функций.</span><span class="sxs-lookup"><span data-stu-id="50f68-135">[Azure App Configuration](https://docs.microsoft.com/azure/azure-app-configuration/overview) provides a centralized repository for feature flags.</span></span> <span data-ttu-id="50f68-136">С его помощью вы можете быстро и уверенно определять различные типы флагов функций и манипулировать их состояниями.</span><span class="sxs-lookup"><span data-stu-id="50f68-136">With it, you define different kinds of feature flags and manipulate their states quickly and confidently.</span></span> <span data-ttu-id="50f68-137">Добавьте клиентские библиотеки конфигурации приложений в приложение, чтобы включить функцию флагов компонентов.</span><span class="sxs-lookup"><span data-stu-id="50f68-137">You add the App Configuration client libraries to your application to enable feature flag functionality.</span></span> <span data-ttu-id="50f68-138">Поддерживаются различные платформы языка программирования.</span><span class="sxs-lookup"><span data-stu-id="50f68-138">Various programming language frameworks are supported.</span></span>

<span data-ttu-id="50f68-139">Флаги компонентов можно легко реализовать в [службе ASP.NET Core](https://docs.microsoft.com/azure/azure-app-configuration/use-feature-flags-dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="50f68-139">Feature flags can be easily implemented in an [ASP.NET Core service](https://docs.microsoft.com/azure/azure-app-configuration/use-feature-flags-dotnet-core).</span></span> <span data-ttu-id="50f68-140">Установка библиотек управления функциями .NET и поставщика конфигурации приложений позволяет декларативно добавлять в код флаги компонентов.</span><span class="sxs-lookup"><span data-stu-id="50f68-140">Installing the .NET Feature Management libraries and App Configuration provider enable you to declaratively add feature flags to your code.</span></span> <span data-ttu-id="50f68-141">Они включают `FeatureGate` атрибуты, чтобы не нужно было вручную писать операторы if в базе кода.</span><span class="sxs-lookup"><span data-stu-id="50f68-141">They enable `FeatureGate` attributes so that you don't have to manually write if statements across your codebase.</span></span>

<span data-ttu-id="50f68-142">После настройки в классе Startup можно добавить функциональные возможности флагов компонентов на уровне контроллера, действия или по промежуточного слоя.</span><span class="sxs-lookup"><span data-stu-id="50f68-142">Once configured in your Startup class, you can add feature flag functionality at the controller, action, or middleware level.</span></span> <span data-ttu-id="50f68-143">На рисунке 10-12 представлена реализация контроллера и действия:</span><span class="sxs-lookup"><span data-stu-id="50f68-143">Figure 10-12 presents controller and action implementation:</span></span>

```c#
[FeatureGate(MyFeatureFlags.FeatureA)]
public class ProductController : Controller
{
    ...
}
```

```c#
[FeatureGate(MyFeatureFlags.FeatureA)]
public IActionResult UpdateProductStatus()
{
    return ObjectResult(ProductDto);
}
```

<span data-ttu-id="50f68-144">**Рис. 10-12** . Реализация флага функции в контроллере и действии.</span><span class="sxs-lookup"><span data-stu-id="50f68-144">**Figure 10-12** - Feature flag implementation in a controller and action.</span></span>

<span data-ttu-id="50f68-145">Если флаг функции отключен, пользователь получит код состояния 404 (не найдено) без текста ответа.</span><span class="sxs-lookup"><span data-stu-id="50f68-145">If a feature flag is disabled, the user will receive a 404 (Not Found) status code with no response body.</span></span>

<span data-ttu-id="50f68-146">Флаги компонентов также можно внедрять непосредственно в классы C#.</span><span class="sxs-lookup"><span data-stu-id="50f68-146">Feature flags can also be injected directly into C# classes.</span></span> <span data-ttu-id="50f68-147">На рис. 10-13 показано внедрение флагов функций:</span><span class="sxs-lookup"><span data-stu-id="50f68-147">Figure 10-13 shows feature flag injection:</span></span>

```c#
public class ProductController : Controller
{
    private readonly IFeatureManager _featureManager;

    public ProductController(IFeatureManager featureManager)
    {
        _featureManager = featureManager;
    }
}
```

<span data-ttu-id="50f68-148">**Рис. 10-13** . Встраивание флага функции в класс.</span><span class="sxs-lookup"><span data-stu-id="50f68-148">**Figure 10-13** - Feature flag injection into a class.</span></span>

<span data-ttu-id="50f68-149">Библиотеки управления функциями управляют жизненным циклом флага компонента в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="50f68-149">The Feature Management libraries manage the feature flag lifecycle behind the scenes.</span></span> <span data-ttu-id="50f68-150">Например, чтобы максимально ограничить большое число вызовов хранилища конфигурации, в библиотеках флаги кэшируют состояние на указанный период времени.</span><span class="sxs-lookup"><span data-stu-id="50f68-150">For example, to minimize high numbers of calls to the configuration store, the libraries cache flag states for a specified duration.</span></span> <span data-ttu-id="50f68-151">Они могут гарантировать неизменность состояний флага во время вызова запроса.</span><span class="sxs-lookup"><span data-stu-id="50f68-151">They can guarantee the immutability of flag states during a request call.</span></span> <span data-ttu-id="50f68-152">Они также предлагают `Point-in-time snapshot` .</span><span class="sxs-lookup"><span data-stu-id="50f68-152">They also offer a `Point-in-time snapshot`.</span></span> <span data-ttu-id="50f68-153">Вы можете восстановить историю любого значения ключа и предоставить свое значение в любое время в течение предыдущих семи дней.</span><span class="sxs-lookup"><span data-stu-id="50f68-153">You can reconstruct the history of any key-value and provide its past value at any moment within the previous seven days.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="50f68-154">[Назад](devops.md)
>[Вперед](infrastructure-as-code.md)</span><span class="sxs-lookup"><span data-stu-id="50f68-154">[Previous](devops.md)
[Next](infrastructure-as-code.md)</span></span>

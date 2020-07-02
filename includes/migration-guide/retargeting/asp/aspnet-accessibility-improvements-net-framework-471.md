---
ms.openlocfilehash: 418bcdca1e9a325894891d7b0e080ce035e2d1b4
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614681"
---
### <a name="aspnet-accessibility-improvements-in-net-framework-471"></a><span data-ttu-id="88ff3-101">Усовершенствованные специальные возможности ASP.NET в .NET Framework 4.7.1</span><span class="sxs-lookup"><span data-stu-id="88ff3-101">ASP.NET Accessibility Improvements in .NET Framework 4.7.1</span></span>

#### <a name="details"></a><span data-ttu-id="88ff3-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="88ff3-102">Details</span></span>

<span data-ttu-id="88ff3-103">Начиная с .NET Framework 4.7.1 в ASP.NET улучшена работа веб-элементов управления ASP.NET с технологией специальных возможностей в Visual Studio для удобства клиентов ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="88ff3-103">Starting with the .NET Framework 4.7.1, ASP.NET has improved how ASP.NET Web Controls work with accessibility technology in Visual Studio to better support ASP.NET customers.</span></span>  <span data-ttu-id="88ff3-104">Внесены следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="88ff3-104">These include the following changes:</span></span>

- <span data-ttu-id="88ff3-105">Изменения для реализации отсутствующих шаблонов специальных возможностей пользовательского интерфейса в элементах управления, например в диалоговом окне "Добавить поле" в мастере представления сведений или в диалоговом окне "Настройка ListView" в мастере ListView.</span><span class="sxs-lookup"><span data-stu-id="88ff3-105">Changes to implement missing UI accessibility patterns in controls, like the Add Field dialog in the Details View wizard, or the Configure ListView dialog of the ListView wizard.</span></span>
- <span data-ttu-id="88ff3-106">Изменения для улучшенного отображения в режиме высокой контрастности, например в редакторе полей страничного навигатора данных.</span><span class="sxs-lookup"><span data-stu-id="88ff3-106">Changes to improve the display in High Contrast mode, like the Data Pager Fields Editor.</span></span>
- <span data-ttu-id="88ff3-107">Изменения для улучшения навигации с помощью клавиатуры для таких элементов, как диалоговое окно "Поля" в мастере "Изменить поля страничного навигатора" средства управления DataPager, диалоговое окно "Настройка ObjectContext" или диалоговое окно "Настройка выбора данных" в мастере "Настройка источника данных".</span><span class="sxs-lookup"><span data-stu-id="88ff3-107">Changes to improve the keyboard navigation experiences for controls, like the Fields dialog in the Edit Pager Fields wizard of the DataPager control, the Configure ObjectContext dialog, or the Configure Data Selection dialog of the Configure Data Source wizard.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="88ff3-108">Предложение</span><span class="sxs-lookup"><span data-stu-id="88ff3-108">Suggestion</span></span>

<span data-ttu-id="88ff3-109">**Как принять или отклонить изменения** Чтобы эти изменения можно было использовать в конструкторе Visual Studio, он должен быть запущен на платформе .NET Framework 4.7.1 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="88ff3-109">**How to opt in or out of these changes** In order for the Visual Studio Designer to benefit from these changes, it must run on the .NET Framework 4.7.1 or later.</span></span> <span data-ttu-id="88ff3-110">В веб-приложении эти изменения можно использовать одним из следующих способов:</span><span class="sxs-lookup"><span data-stu-id="88ff3-110">The web application can benefit from these changes in either of the following ways:</span></span>

- <span data-ttu-id="88ff3-111">Установите Visual Studio 2017 15.3 или более поздней версии, которая поддерживает новые функции специальных возможностей со следующим переключателем AppContext по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="88ff3-111">Install Visual Studio 2017 15.3 or later, which supports the new accessibility features with the following AppContext Switch by default.</span></span>
- <span data-ttu-id="88ff3-112">Откажитесь от функций специальных возможностей в предыдущих версиях, добавив переключатель AppContext `Switch.UseLegacyAccessibilityFeatures` в раздел `<runtime>` файла конфигурации devenv.exe.config и установив значение `false`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="88ff3-112">Opt out of the legacy accessibility behaviors by adding the `Switch.UseLegacyAccessibilityFeatures` AppContext switch to the `<runtime>` section in the devenv.exe.config file and setting it to `false`, as the following example shows.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
<runtime>
...
<!-- AppContextSwitchOverrides value attribute is in the form of 'key1=true/false;key2=true/false'  -->
<AppContextSwitchOverrides value="Switch.UseLegacyAccessibilityFeatures=false" />
...
</runtime>
</configuration>
```

<span data-ttu-id="88ff3-113">В приложениях, предназначенных для .NET Framework 4.7.1 или более поздней версии, где требуется сохранить предыдущие функции специальных возможностей, можно выбрать прежние функции специальных возможностей, явно установив этот переключатель AppContext в значение `true`.</span><span class="sxs-lookup"><span data-stu-id="88ff3-113">Applications that target the .NET Framework 4.7.1 or later and want to preserve the legacy accessibility behavior can opt in to the use of legacy accessibility features by explicitly setting this AppContext switch to `true`.</span></span>

| <span data-ttu-id="88ff3-114">name</span><span class="sxs-lookup"><span data-stu-id="88ff3-114">Name</span></span>    | <span data-ttu-id="88ff3-115">Значение</span><span class="sxs-lookup"><span data-stu-id="88ff3-115">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="88ff3-116">Область</span><span class="sxs-lookup"><span data-stu-id="88ff3-116">Scope</span></span>   | <span data-ttu-id="88ff3-117">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="88ff3-117">Minor</span></span>       |
| <span data-ttu-id="88ff3-118">Версия</span><span class="sxs-lookup"><span data-stu-id="88ff3-118">Version</span></span> | <span data-ttu-id="88ff3-119">4.7.1</span><span class="sxs-lookup"><span data-stu-id="88ff3-119">4.7.1</span></span>       |
| <span data-ttu-id="88ff3-120">Type</span><span class="sxs-lookup"><span data-stu-id="88ff3-120">Type</span></span>    | <span data-ttu-id="88ff3-121">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="88ff3-121">Retargeting</span></span> |

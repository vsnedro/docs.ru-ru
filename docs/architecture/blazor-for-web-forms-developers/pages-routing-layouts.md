---
title: Страницы, маршрутизация и макеты
description: Узнайте, как создавать страницы в Blazor , работать с маршрутизацией на стороне клиента и управлять макетами страниц.
author: danroth27
ms.author: daroth
no-loc:
- Blazor
ms.date: 09/19/2019
ms.openlocfilehash: fc1f6f9420c7149b6e67123f2f68bef75667aa0c
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173111"
---
# <a name="pages-routing-and-layouts"></a><span data-ttu-id="cc401-103">Страницы, маршрутизация и макеты</span><span class="sxs-lookup"><span data-stu-id="cc401-103">Pages, routing, and layouts</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="cc401-104">ASP.NET приложения Web Forms состоят из страниц, определенных в *ASPX* -файлах.</span><span class="sxs-lookup"><span data-stu-id="cc401-104">ASP.NET Web Forms apps are composed of pages defined in *.aspx* files.</span></span> <span data-ttu-id="cc401-105">Адрес каждой страницы зависит от его физического пути к файлу в проекте.</span><span class="sxs-lookup"><span data-stu-id="cc401-105">Each page's address is based on its physical file path in the project.</span></span> <span data-ttu-id="cc401-106">Когда браузер выполняет запрос к странице, содержимое страницы динамически отображается на сервере.</span><span class="sxs-lookup"><span data-stu-id="cc401-106">When a browser makes a request to the page, the contents of the page are dynamically rendered on the server.</span></span> <span data-ttu-id="cc401-107">Учетные записи отрисовки как HTML-разметки страницы, так и ее серверных элементов управления.</span><span class="sxs-lookup"><span data-stu-id="cc401-107">The rendering accounts for both the page's HTML markup and its server controls.</span></span>

<span data-ttu-id="cc401-108">В Blazor каждая страница в приложении является компонентом, обычно определяемым в файле *Razor* , с одним или несколькими указанными маршрутами.</span><span class="sxs-lookup"><span data-stu-id="cc401-108">In Blazor, each page in the app is a component, typically defined in a *.razor* file, with one or more specified routes.</span></span> <span data-ttu-id="cc401-109">Маршрутизация в основном происходит на стороне клиента без участия конкретного запроса сервера.</span><span class="sxs-lookup"><span data-stu-id="cc401-109">Routing mostly happens client-side without involving a specific server request.</span></span> <span data-ttu-id="cc401-110">Сначала браузер выполняет запрос к корневому адресу приложения.</span><span class="sxs-lookup"><span data-stu-id="cc401-110">The browser first makes a request to the root address of the app.</span></span> <span data-ttu-id="cc401-111">Затем корневой `Router` компонент в Blazor приложении обрабатывает перехват запросов навигации и их в нужный компонент.</span><span class="sxs-lookup"><span data-stu-id="cc401-111">A root `Router` component in the Blazor app then handles intercepting navigation requests and them to the correct component.</span></span>

Blazor<span data-ttu-id="cc401-112">также поддерживает *глубокую компоновку*.</span><span class="sxs-lookup"><span data-stu-id="cc401-112"> also supports *deep linking*.</span></span> <span data-ttu-id="cc401-113">Глубокое связывание происходит, когда браузер выполняет запрос к конкретному маршруту, отличному от корневого каталога приложения.</span><span class="sxs-lookup"><span data-stu-id="cc401-113">Deep linking occurs when the browser makes a request to a specific route other than the root of the app.</span></span> <span data-ttu-id="cc401-114">Запросы на детализированные ссылки, отправленные на сервер, направляются в Blazor приложение, которое затем направляет клиентский запрос к нужному компоненту.</span><span class="sxs-lookup"><span data-stu-id="cc401-114">Requests for deep links sent to the server are routed to the Blazor app, which then routes the request client-side to the correct component.</span></span>

<span data-ttu-id="cc401-115">Простая страница в веб-формах ASP.NET может содержать следующую разметку:</span><span class="sxs-lookup"><span data-stu-id="cc401-115">A simple page in ASP.NET Web Forms might contain the following markup:</span></span>

<span data-ttu-id="cc401-116">*Имя. aspx*</span><span class="sxs-lookup"><span data-stu-id="cc401-116">*Name.aspx*</span></span>

```aspx-csharp
<%@ Page Title="Name" Language="C#" MasterPageFile="~/Site.Master" AutoEventWireup="true" CodeBehind="Name.aspx.cs" Inherits="WebApplication1.Name" %>

<asp:Content ID="BodyContent" ContentPlaceHolderID="MainContent" runat="server">
    <div>
        What is your name?<br />
        <asp:TextBox ID="TextBox1" runat="server"></asp:TextBox>
        <asp:Button ID="Button1" runat="server" Text="Submit" OnClick="Button1_Click" />
    </div>
    <div>
        <asp:Literal ID="Literal1" runat="server" />
    </div>
</asp:Content>
```

<span data-ttu-id="cc401-117">*Name.aspx.cs*</span><span class="sxs-lookup"><span data-stu-id="cc401-117">*Name.aspx.cs*</span></span>

```csharp
public partial class Name : System.Web.UI.Page
{
    protected void Button1_Click1(object sender, EventArgs e)
    {
        Literal1.Text = "Hello " + TextBox1.Text;
    }
}
```

<span data-ttu-id="cc401-118">Эквивалентная страница в Blazor приложении будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cc401-118">The equivalent page in a Blazor app would look like this:</span></span>

<span data-ttu-id="cc401-119">*Name. Razor*</span><span class="sxs-lookup"><span data-stu-id="cc401-119">*Name.razor*</span></span>

```razor
@page "/Name"
@layout MainLayout

<div>
    What is your name?<br />
    <input @bind="text" />
    <button @onclick="OnClick">Submit</button>
</div>
<div>
    @if (name != null)
    {
        @:Hello @name
    }
</div>

@code {
    string text;
    string name;

    void OnClick() {
        name = text;
    }
}
```

## <a name="create-pages"></a><span data-ttu-id="cc401-120">Создание страниц</span><span class="sxs-lookup"><span data-stu-id="cc401-120">Create pages</span></span>

<span data-ttu-id="cc401-121">Чтобы создать страницу в Blazor , создайте компонент и добавьте `@page` директиву Razor, чтобы указать маршрут для компонента.</span><span class="sxs-lookup"><span data-stu-id="cc401-121">To create a page in Blazor, create a component and add the `@page` Razor directive to specify the route for the component.</span></span> <span data-ttu-id="cc401-122">`@page`Директива принимает один параметр, который является шаблоном маршрута, добавляемым к этому компоненту.</span><span class="sxs-lookup"><span data-stu-id="cc401-122">The `@page` directive takes a single parameter, which is the route template to add to that component.</span></span>

```razor
@page "/counter"
```

<span data-ttu-id="cc401-123">Параметр шаблона Route является обязательным.</span><span class="sxs-lookup"><span data-stu-id="cc401-123">The route template parameter is required.</span></span> <span data-ttu-id="cc401-124">В отличие от веб-форм ASP.NET, маршрут к Blazor компоненту *не* определяется местоположением файла (хотя это может быть компонент, добавляемый в будущем).</span><span class="sxs-lookup"><span data-stu-id="cc401-124">Unlike ASP.NET Web Forms, the route to a Blazor component *isn't* inferred from its file location (although that may be a feature added in the future).</span></span>

<span data-ttu-id="cc401-125">Синтаксис шаблона маршрута — это тот же базовый синтаксис, который используется для маршрутизации в веб-формах ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cc401-125">The route template syntax is the same basic syntax used for routing in ASP.NET Web Forms.</span></span> <span data-ttu-id="cc401-126">Параметры маршрута указываются в шаблоне с помощью фигурных скобок.</span><span class="sxs-lookup"><span data-stu-id="cc401-126">Route parameters are specified in the template using braces.</span></span> Blazor<span data-ttu-id="cc401-127">привязывает значения маршрута к параметрам компонента с тем же именем (без учета регистра).</span><span class="sxs-lookup"><span data-stu-id="cc401-127"> will bind route values to component parameters with the same name (case-insensitive).</span></span>

```razor
@page "/product/{id}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public string Id { get; set; }
}
```

<span data-ttu-id="cc401-128">Можно также указать ограничения на значение параметра Route.</span><span class="sxs-lookup"><span data-stu-id="cc401-128">You can also specify constraints on the value of the route parameter.</span></span> <span data-ttu-id="cc401-129">Например, чтобы ограничить идентификатор продукта, `int` сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="cc401-129">For example, to constrain the product ID to be an `int`:</span></span>

```razor
@page "/product/{id:int}"

<h1>Product @Id</h1>

@code {
    [Parameter]
    public int Id { get; set; }
}
```

<span data-ttu-id="cc401-130">Полный список ограничений маршрута Blazor , поддерживаемых, см. в разделе [ограничения маршрутов](/aspnet/core/blazor/routing#route-constraints).</span><span class="sxs-lookup"><span data-stu-id="cc401-130">For a full list of the route constraints supported by Blazor, see [Route constraints](/aspnet/core/blazor/routing#route-constraints).</span></span>

## <a name="router-component"></a><span data-ttu-id="cc401-131">Компонент маршрутизатора</span><span class="sxs-lookup"><span data-stu-id="cc401-131">Router component</span></span>

<span data-ttu-id="cc401-132">Маршрутизация в Blazor обрабатывается `Router` компонентом.</span><span class="sxs-lookup"><span data-stu-id="cc401-132">Routing in Blazor is handled by the `Router` component.</span></span> <span data-ttu-id="cc401-133">`Router`Компонент обычно используется в корневом компоненте приложения (*app. Razor*).</span><span class="sxs-lookup"><span data-stu-id="cc401-133">The `Router` component is typically used in the app's root component (*App.razor*).</span></span>

```razor
<Router AppAssembly="@typeof(Program).Assembly">
    <Found Context="routeData">
        <RouteView RouteData="@routeData" DefaultLayout="@typeof(MainLayout)" />
    </Found>
    <NotFound>
        <LayoutView Layout="@typeof(MainLayout)">
            <p>Sorry, there's nothing at this address.</p>
        </LayoutView>
    </NotFound>
</Router>
```

<span data-ttu-id="cc401-134">`Router`Компонент обнаруживает маршрутизируемый компоненты в указанном `AppAssembly` и в дополнительно указанном параметре `AdditionalAssemblies` .</span><span class="sxs-lookup"><span data-stu-id="cc401-134">The `Router` component discovers the routable components in the specified `AppAssembly` and in the optionally specified `AdditionalAssemblies`.</span></span> <span data-ttu-id="cc401-135">При переходе в браузере объект `Router` перехватывает навигацию и отображает содержимое его `Found` параметра с извлеченным, `RouteData` Если маршрут соответствует адресу, в противном случае — `Router` отрисовывает свой `NotFound` параметр.</span><span class="sxs-lookup"><span data-stu-id="cc401-135">When the browser navigates, the `Router` intercepts the navigation and renders the contents of its `Found` parameter with the extracted `RouteData` if a route matches the address, otherwise the `Router` renders its `NotFound` parameter.</span></span>

<span data-ttu-id="cc401-136">`RouteView`Компонент обрабатывает сопоставленный компонент, указанный в, `RouteData` с его макетом, если он имеется.</span><span class="sxs-lookup"><span data-stu-id="cc401-136">The `RouteView` component handles rendering the matched component specified by the `RouteData` with its layout if it has one.</span></span> <span data-ttu-id="cc401-137">Если сопоставляемый компонент не имеет макета, используется дополнительно указанный параметр `DefaultLayout` .</span><span class="sxs-lookup"><span data-stu-id="cc401-137">If the matched component doesn't have a layout, then the optionally specified `DefaultLayout` is used.</span></span>

<span data-ttu-id="cc401-138">`LayoutView`Компонент визуализирует свое дочернее содержимое в указанном макете.</span><span class="sxs-lookup"><span data-stu-id="cc401-138">The `LayoutView` component renders its child content within the specified layout.</span></span> <span data-ttu-id="cc401-139">Далее в этой главе мы рассмотрим макеты более подробно.</span><span class="sxs-lookup"><span data-stu-id="cc401-139">We'll look at layouts more in detail later in this chapter.</span></span>

## <a name="navigation"></a><span data-ttu-id="cc401-140">Навигация</span><span class="sxs-lookup"><span data-stu-id="cc401-140">Navigation</span></span>

<span data-ttu-id="cc401-141">В ASP.NET Web Forms вы запускаете навигацию на другой странице, возвращая ответ перенаправления в браузер.</span><span class="sxs-lookup"><span data-stu-id="cc401-141">In ASP.NET Web Forms, you trigger navigation to a different page by returning a redirect response to the browser.</span></span> <span data-ttu-id="cc401-142">Пример.</span><span class="sxs-lookup"><span data-stu-id="cc401-142">For example:</span></span>

```csharp
protected void NavigateButton_Click(object sender, EventArgs e)
{
    Response.Redirect("Counter");
}
```

<span data-ttu-id="cc401-143">Возврат ответа перенаправления обычно не поддерживается в Blazor .</span><span class="sxs-lookup"><span data-stu-id="cc401-143">Returning a redirect response isn't typically possible in Blazor.</span></span> Blazor<span data-ttu-id="cc401-144">не использует модель "запрос-ответ".</span><span class="sxs-lookup"><span data-stu-id="cc401-144"> doesn't use a request-reply model.</span></span> <span data-ttu-id="cc401-145">Однако вы можете активировать навигацию в браузере напрямую, как и в случае с JavaScript.</span><span class="sxs-lookup"><span data-stu-id="cc401-145">You can, however, trigger browser navigations directly, as you can with JavaScript.</span></span>

Blazor<span data-ttu-id="cc401-146">предоставляет `NavigationManager` службу, которую можно использовать для:</span><span class="sxs-lookup"><span data-stu-id="cc401-146"> provides a `NavigationManager` service that can be used to:</span></span>

- <span data-ttu-id="cc401-147">Получить текущий адрес браузера</span><span class="sxs-lookup"><span data-stu-id="cc401-147">Get the current browser address</span></span>
- <span data-ttu-id="cc401-148">Получить базовый адрес</span><span class="sxs-lookup"><span data-stu-id="cc401-148">Get the base address</span></span>
- <span data-ttu-id="cc401-149">Переходы по триггерам</span><span class="sxs-lookup"><span data-stu-id="cc401-149">Trigger navigations</span></span>
- <span data-ttu-id="cc401-150">Получать уведомления при изменении адреса</span><span class="sxs-lookup"><span data-stu-id="cc401-150">Get notified when the address changes</span></span>

<span data-ttu-id="cc401-151">Для перехода к другому адресу используйте `NavigateTo` метод:</span><span class="sxs-lookup"><span data-stu-id="cc401-151">To navigate to a different address, use the `NavigateTo` method:</span></span>

```razor
@page "/"
@inject NavigationManager NavigationManager

<button @onclick="Navigate">Navigate</button>

@code {
    void Navigate() {
        NavigationManager.NavigateTo("counter");
    }
}
```

<span data-ttu-id="cc401-152">Описание всех `NavigationManager` членов см. в разделе [вспомогательные методы состояния URI и навигации](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers).</span><span class="sxs-lookup"><span data-stu-id="cc401-152">For a description of all `NavigationManager` members, see [URI and navigation state helpers](/aspnet/core/blazor/routing#uri-and-navigation-state-helpers).</span></span>

## <a name="base-urls"></a><span data-ttu-id="cc401-153">Базовые URL-адреса</span><span class="sxs-lookup"><span data-stu-id="cc401-153">Base URLs</span></span>

<span data-ttu-id="cc401-154">Если Blazor приложение развертывается по базовому пути, необходимо указать базовый URL-адрес в метаданных страницы с помощью `<base>` тега для свойства маршрутизации к работе.</span><span class="sxs-lookup"><span data-stu-id="cc401-154">If your Blazor app is deployed under a base path, then you need to specify the base URL in the page metadata using the `<base>` tag for routing to work property.</span></span> <span data-ttu-id="cc401-155">Если страница узла для приложения отображается на сервере с помощью Razor, то можно использовать `~/` синтаксис для указания базового адреса приложения.</span><span class="sxs-lookup"><span data-stu-id="cc401-155">If the host page for the app is server-rendered using Razor, then you can use the `~/` syntax to specify the app's base address.</span></span> <span data-ttu-id="cc401-156">Если страница узла является статическим HTML, необходимо явно указать базовый URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="cc401-156">If the host page is static HTML, then you need to specify the base URL explicitly.</span></span>

```html
<base href="~/" />
```

## <a name="page-layout"></a><span data-ttu-id="cc401-157">Макет страницы</span><span class="sxs-lookup"><span data-stu-id="cc401-157">Page layout</span></span>

<span data-ttu-id="cc401-158">Макет страницы в веб-формах ASP.NET обрабатывается главными страницами.</span><span class="sxs-lookup"><span data-stu-id="cc401-158">Page layout in ASP.NET Web Forms is handled by Master Pages.</span></span> <span data-ttu-id="cc401-159">Главные страницы определяют шаблон с одним или несколькими заполнителями содержимого, которые затем могут быть предоставлены отдельными страницами.</span><span class="sxs-lookup"><span data-stu-id="cc401-159">Master Pages define a template with one or more content placeholders that can then be supplied by individual pages.</span></span> <span data-ttu-id="cc401-160">Главные страницы определяются в файлах *master* и начинаются с `<%@ Master %>` директивы.</span><span class="sxs-lookup"><span data-stu-id="cc401-160">Master Pages are defined in *.master* files and start with the `<%@ Master %>` directive.</span></span> <span data-ttu-id="cc401-161">Содержимое *главных* файлов задается как страница *ASPX* , но с добавлением `<asp:ContentPlaceHolder>` элементов управления для пометки места, где страницы могут предоставлять содержимое.</span><span class="sxs-lookup"><span data-stu-id="cc401-161">The content of the *.master* files is coded as you would an *.aspx* page, but with the addition of `<asp:ContentPlaceHolder>` controls to mark where pages can supply content.</span></span>

<span data-ttu-id="cc401-162">*Site.master*</span><span class="sxs-lookup"><span data-stu-id="cc401-162">*Site.master*</span></span>

```aspx-csharp
<%@ Master Language="C#" AutoEventWireup="true" CodeBehind="Site.master.cs" Inherits="WebApplication1.SiteMaster" %>

<!DOCTYPE html>
<html lang="en">
<head runat="server">
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title><%: Page.Title %> - My ASP.NET Application</title>
    <link href="~/favicon.ico" rel="shortcut icon" type="image/x-icon" />
</head>
<body>
    <form runat="server">
        <div class="container body-content">
            <asp:ContentPlaceHolder ID="MainContent" runat="server">
            </asp:ContentPlaceHolder>
            <hr />
            <footer>
                <p>&copy; <%: DateTime.Now.Year %> - My ASP.NET Application</p>
            </footer>
        </div>
    </form>
</body>
</html>
```

<span data-ttu-id="cc401-163">В Blazor среде макет страницы обрабатывается с помощью компонентов макета.</span><span class="sxs-lookup"><span data-stu-id="cc401-163">In Blazor, you handle page layout using layout components.</span></span> <span data-ttu-id="cc401-164">Компоненты макета наследуют от класса `LayoutComponentBase` , который определяет одно `Body` свойство типа `RenderFragment` , которое можно использовать для визуализации содержимого страницы.</span><span class="sxs-lookup"><span data-stu-id="cc401-164">Layout components inherit from `LayoutComponentBase`, which defines a single `Body` property of type `RenderFragment`, which can be used to render the contents of the page.</span></span>

<span data-ttu-id="cc401-165">*Маинлайаут. Razor*</span><span class="sxs-lookup"><span data-stu-id="cc401-165">*MainLayout.razor*</span></span>

```razor
@inherits LayoutComponentBase
<h1>Main layout</h1>
<div>
    @Body
</div>
```

<span data-ttu-id="cc401-166">При отображении страницы с макетом Эта страница подготавливается к просмотру в пределах содержимого указанного макета в расположении, в котором макет визуализирует свое `Body` свойство.</span><span class="sxs-lookup"><span data-stu-id="cc401-166">When the page with a layout is rendered, the page is rendered within the contents of the specified layout at the location where the layout renders its `Body` property.</span></span>

<span data-ttu-id="cc401-167">Чтобы применить макет к странице, используйте `@layout` директиву:</span><span class="sxs-lookup"><span data-stu-id="cc401-167">To apply a layout to a page, use the `@layout` directive:</span></span>

```razor
@layout MainLayout
```

<span data-ttu-id="cc401-168">Можно указать макет для всех компонентов в папке и вложенных папках, используя файл *_Imports. Razor* .</span><span class="sxs-lookup"><span data-stu-id="cc401-168">You can specify the layout for all components in a folder and subfolders using an *_Imports.razor* file.</span></span> <span data-ttu-id="cc401-169">Можно также указать макет по умолчанию для всех страниц с помощью [компонента маршрутизатора](#router-component).</span><span class="sxs-lookup"><span data-stu-id="cc401-169">You can also specify a default layout for all your pages using the [Router component](#router-component).</span></span>

<span data-ttu-id="cc401-170">Главные страницы могут определять несколько заполнителей содержимого, но макеты Blazor имеют только одно `Body` свойство.</span><span class="sxs-lookup"><span data-stu-id="cc401-170">Master Pages can define multiple content placeholders, but layouts in Blazor only have a single `Body` property.</span></span> <span data-ttu-id="cc401-171">Это ограничение Blazor в отношении компонентов макета будет рассмотрено в следующем выпуске.</span><span class="sxs-lookup"><span data-stu-id="cc401-171">This limitation of Blazor layout components will hopefully be addressed in a future release.</span></span>

<span data-ttu-id="cc401-172">Главные страницы в веб-формах ASP.NET могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="cc401-172">Master Pages in ASP.NET Web Forms can be nested.</span></span> <span data-ttu-id="cc401-173">То есть Главная страница может также использовать главную страницу.</span><span class="sxs-lookup"><span data-stu-id="cc401-173">That is, a Master Page may also use a Master Page.</span></span> <span data-ttu-id="cc401-174">Компоненты макета в Blazor могут быть вложенными.</span><span class="sxs-lookup"><span data-stu-id="cc401-174">Layout components in Blazor may be nested too.</span></span> <span data-ttu-id="cc401-175">Компонент макета можно применить к компоненту макета.</span><span class="sxs-lookup"><span data-stu-id="cc401-175">You can apply a layout component to a layout component.</span></span> <span data-ttu-id="cc401-176">Содержимое внутреннего макета будет отображаться во внешнем макете.</span><span class="sxs-lookup"><span data-stu-id="cc401-176">The contents of the inner layout will be rendered within the outer layout.</span></span>

<span data-ttu-id="cc401-177">*Чилдлайаут. Razor*</span><span class="sxs-lookup"><span data-stu-id="cc401-177">*ChildLayout.razor*</span></span>

```razor
@layout MainLayout
<h2>Child layout</h2>
<div>
    @Body
</div>
```

<span data-ttu-id="cc401-178">*Index. Razor*</span><span class="sxs-lookup"><span data-stu-id="cc401-178">*Index.razor*</span></span>

```razor
@page "/"
@layout ChildLayout
<p>I'm in a nested layout!</p>
```

<span data-ttu-id="cc401-179">Отображаемые выходные данные для страницы будут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="cc401-179">The rendered output for the page would then be:</span></span>

```html
<h1>Main layout</h1>
<div>
    <h2>Child layout</h2>
    <div>
        <p>I'm in a nested layout!</p>
    </div>
</div>
```

<span data-ttu-id="cc401-180">Макеты в Blazor обычно не определяют корневые элементы HTML для страницы ( `<html>` , `<body>` , `<head>` и т. д.).</span><span class="sxs-lookup"><span data-stu-id="cc401-180">Layouts in Blazor don't typically define the root HTML elements for a page (`<html>`, `<body>`, `<head>`, and so on).</span></span> <span data-ttu-id="cc401-181">Корневые элементы HTML определяются на Blazor странице узла приложения, которая используется для отрисовки начального содержимого HTML для приложения (см. раздел [Начальная Blazor ](project-structure.md#bootstrap-blazor)загрузка).</span><span class="sxs-lookup"><span data-stu-id="cc401-181">The root HTML elements are instead defined in a Blazor app's host page, which is used to render the initial HTML content for the app (see [Bootstrap Blazor](project-structure.md#bootstrap-blazor)).</span></span> <span data-ttu-id="cc401-182">Страница узла может визуализировать несколько корневых компонентов для приложения с окружающей разметкой.</span><span class="sxs-lookup"><span data-stu-id="cc401-182">The host page can render multiple root components for the app with surrounding markup.</span></span>

<span data-ttu-id="cc401-183">Компоненты в Blazor , включая страницы, не могут отображать `<script>` теги.</span><span class="sxs-lookup"><span data-stu-id="cc401-183">Components in Blazor, including pages, can't render `<script>` tags.</span></span> <span data-ttu-id="cc401-184">Это ограничение отрисовки существует `<script>` , так как теги загружаются один раз, а затем не могут быть изменены.</span><span class="sxs-lookup"><span data-stu-id="cc401-184">This rendering restriction exists because `<script>` tags get loaded once and then can't be changed.</span></span> <span data-ttu-id="cc401-185">Если вы попытаетесь динамически визуализировать Теги с помощью синтаксис Razor, может произойти непредвиденное поведение.</span><span class="sxs-lookup"><span data-stu-id="cc401-185">Unexpected behavior may occur if you try to render the tags dynamically using Razor syntax.</span></span> <span data-ttu-id="cc401-186">Вместо этого все `<script>` теги должны быть добавлены на страницу узла приложения.</span><span class="sxs-lookup"><span data-stu-id="cc401-186">Instead, all `<script>` tags should be added to the app's host page.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cc401-187">[Назад](components.md)
>[Вперед](state-management.md)</span><span class="sxs-lookup"><span data-stu-id="cc401-187">[Previous](components.md)
[Next](state-management.md)</span></span>

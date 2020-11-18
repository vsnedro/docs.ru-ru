---
title: Соглашения о написании прописными буквами
description: Применение соглашений о капитализации для идентификаторов, составных слов и общих терминов. Узнайте, как работает чувствительность к регистру в .NET.
ms.date: 10/22/2008
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
ms.openlocfilehash: 8df136fb57ad61ddfd87f4dec1f6490c63c3d977
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821532"
---
# <a name="capitalization-conventions"></a><span data-ttu-id="4a4ad-104">Соглашения о написании прописными буквами</span><span class="sxs-lookup"><span data-stu-id="4a4ad-104">Capitalization Conventions</span></span>
<span data-ttu-id="4a4ad-105">Рекомендации в этой главе посвящены созданию простого метода использования, который при единообразном применении делает идентификаторы для типов, членов и параметров простыми для чтения.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-105">The guidelines in this chapter lay out a simple method for using case that, when applied consistently, make identifiers for types, members, and parameters easy to read.</span></span>

## <a name="capitalization-rules-for-identifiers"></a><span data-ttu-id="4a4ad-106">Правила использования прописных букв для идентификаторов</span><span class="sxs-lookup"><span data-stu-id="4a4ad-106">Capitalization Rules for Identifiers</span></span>
 <span data-ttu-id="4a4ad-107">Чтобы отличать слова в идентификаторе, используйте прописные буквы первой буквы каждого слова в идентификаторе.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-107">To differentiate words in an identifier, capitalize the first letter of each word in the identifier.</span></span> <span data-ttu-id="4a4ad-108">Не используйте знаки подчеркивания для различения слов, а также для любого значения в любом месте идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-108">Do not use underscores to differentiate words, or for that matter, anywhere in identifiers.</span></span> <span data-ttu-id="4a4ad-109">Существует два способа для капитализации идентификаторов в зависимости от использования идентификатора.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-109">There are two appropriate ways to capitalize identifiers, depending on the use of the identifier:</span></span>

- <span data-ttu-id="4a4ad-110">паскалкасинг</span><span class="sxs-lookup"><span data-stu-id="4a4ad-110">PascalCasing</span></span>

- <span data-ttu-id="4a4ad-111">камелкасинг</span><span class="sxs-lookup"><span data-stu-id="4a4ad-111">camelCasing</span></span>

 <span data-ttu-id="4a4ad-112">Соглашение Паскалкасинг, используемое для всех идентификаторов, кроме имен параметров, состоит из первых букв каждого слова (включая акронимы длиной более двух букв), как показано в следующих примерах:</span><span class="sxs-lookup"><span data-stu-id="4a4ad-112">The PascalCasing convention, used for all identifiers except parameter names, capitalizes the first character of each word (including acronyms over two letters in length), as shown in the following examples:</span></span>

 `PropertyDescriptor`
 `HtmlTag`

 <span data-ttu-id="4a4ad-113">Для акронимов с двумя буквами используется специальный случай, в котором буквы записываются прописными буквами, как показано в следующем идентификаторе:</span><span class="sxs-lookup"><span data-stu-id="4a4ad-113">A special case is made for two-letter acronyms in which both letters are capitalized, as shown in the following identifier:</span></span>

 `IOStream`

 <span data-ttu-id="4a4ad-114">Соглашение Камелкасинг, используемое только для имен параметров, состоит из первых букв каждого слова, за исключением первого слова, как показано в следующих примерах.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-114">The camelCasing convention, used only for parameter names, capitalizes the first character of each word except the first word, as shown in the following examples.</span></span> <span data-ttu-id="4a4ad-115">Как показано в примере, аббревиатуры с двумя буквами, начинающиеся с символов в стиле Camel, являются строчными.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-115">As the example also shows, two-letter acronyms that begin a camel-cased identifier are both lowercase.</span></span>

 `propertyDescriptor`
 `ioStream`
 `htmlTag`

 <span data-ttu-id="4a4ad-116">✔️ использовать Паскалкасинг для всех имен открытых членов, типов и пространств имен, состоящих из нескольких слов.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-116">✔️ DO use PascalCasing for all public member, type, and namespace names consisting of multiple words.</span></span>

 <span data-ttu-id="4a4ad-117">✔️ использовать Камелкасинг для имен параметров.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-117">✔️ DO use camelCasing for parameter names.</span></span>

 <span data-ttu-id="4a4ad-118">В следующей таблице описаны правила капитализации для различных типов идентификаторов.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-118">The following table describes the capitalization rules for different types of identifiers.</span></span>

|<span data-ttu-id="4a4ad-119">Идентификатор</span><span class="sxs-lookup"><span data-stu-id="4a4ad-119">Identifier</span></span>|<span data-ttu-id="4a4ad-120">Регистр</span><span class="sxs-lookup"><span data-stu-id="4a4ad-120">Casing</span></span>|<span data-ttu-id="4a4ad-121">Пример</span><span class="sxs-lookup"><span data-stu-id="4a4ad-121">Example</span></span>|
|----------------|------------|-------------|
|<span data-ttu-id="4a4ad-122">Пространство имен</span><span class="sxs-lookup"><span data-stu-id="4a4ad-122">Namespace</span></span>|<span data-ttu-id="4a4ad-123">Pascal</span><span class="sxs-lookup"><span data-stu-id="4a4ad-123">Pascal</span></span>|`namespace System.Security { ... }`|
|<span data-ttu-id="4a4ad-124">Тип</span><span class="sxs-lookup"><span data-stu-id="4a4ad-124">Type</span></span>|<span data-ttu-id="4a4ad-125">Pascal</span><span class="sxs-lookup"><span data-stu-id="4a4ad-125">Pascal</span></span>|`public class StreamReader { ... }`|
|<span data-ttu-id="4a4ad-126">Интерфейс</span><span class="sxs-lookup"><span data-stu-id="4a4ad-126">Interface</span></span>|<span data-ttu-id="4a4ad-127">Pascal</span><span class="sxs-lookup"><span data-stu-id="4a4ad-127">Pascal</span></span>|`public interface IEnumerable { ... }`|
|<span data-ttu-id="4a4ad-128">Метод</span><span class="sxs-lookup"><span data-stu-id="4a4ad-128">Method</span></span>|<span data-ttu-id="4a4ad-129">Pascal</span><span class="sxs-lookup"><span data-stu-id="4a4ad-129">Pascal</span></span>|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|
|<span data-ttu-id="4a4ad-130">Свойство</span><span class="sxs-lookup"><span data-stu-id="4a4ad-130">Property</span></span>|<span data-ttu-id="4a4ad-131">Pascal</span><span class="sxs-lookup"><span data-stu-id="4a4ad-131">Pascal</span></span>|`public class String {` <br />  `public int Length { get; }` <br /> `}`|
|<span data-ttu-id="4a4ad-132">Событие</span><span class="sxs-lookup"><span data-stu-id="4a4ad-132">Event</span></span>|<span data-ttu-id="4a4ad-133">Pascal</span><span class="sxs-lookup"><span data-stu-id="4a4ad-133">Pascal</span></span>|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|
|<span data-ttu-id="4a4ad-134">Поле</span><span class="sxs-lookup"><span data-stu-id="4a4ad-134">Field</span></span>|<span data-ttu-id="4a4ad-135">Pascal</span><span class="sxs-lookup"><span data-stu-id="4a4ad-135">Pascal</span></span>|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|
|<span data-ttu-id="4a4ad-136">Значение перечисления</span><span class="sxs-lookup"><span data-stu-id="4a4ad-136">Enum value</span></span>|<span data-ttu-id="4a4ad-137">Pascal</span><span class="sxs-lookup"><span data-stu-id="4a4ad-137">Pascal</span></span>|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|
|<span data-ttu-id="4a4ad-138">Параметр</span><span class="sxs-lookup"><span data-stu-id="4a4ad-138">Parameter</span></span>|<span data-ttu-id="4a4ad-139">"верблюжий" стиль.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-139">Camel</span></span>|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|

## <a name="capitalizing-compound-words-and-common-terms"></a><span data-ttu-id="4a4ad-140">Преобразование сложных слов и общих терминов в прописные</span><span class="sxs-lookup"><span data-stu-id="4a4ad-140">Capitalizing Compound Words and Common Terms</span></span>
 <span data-ttu-id="4a4ad-141">Большинство составных терминов рассматриваются как отдельные слова в целях капитализации.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-141">Most compound terms are treated as single words for purposes of capitalization.</span></span>

 <span data-ttu-id="4a4ad-142">❌ НЕ используйте прописные буквы в каждом слове так называемых составных слов с закрытой формой.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-142">❌ DO NOT capitalize each word in so-called closed-form compound words.</span></span>

 <span data-ttu-id="4a4ad-143">Это составные слова, написанные как одно слово, например конечная точка.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-143">These are compound words written as a single word, such as endpoint.</span></span> <span data-ttu-id="4a4ad-144">В соответствии с рекомендациями по регистру рассматривайте составное слово с закрытой формой как одно слово.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-144">For the purpose of casing guidelines, treat a closed-form compound word as a single word.</span></span> <span data-ttu-id="4a4ad-145">Используйте текущий словарь, чтобы определить, написано ли составное слово в закрытой форме.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-145">Use a current dictionary to determine if a compound word is written in closed form.</span></span>

|<span data-ttu-id="4a4ad-146">Pascal</span><span class="sxs-lookup"><span data-stu-id="4a4ad-146">Pascal</span></span>|<span data-ttu-id="4a4ad-147">"верблюжий" стиль.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-147">Camel</span></span>|<span data-ttu-id="4a4ad-148">not</span><span class="sxs-lookup"><span data-stu-id="4a4ad-148">Not</span></span>|
|------------|-----------|---------|
|`BitFlag`|`bitFlag`|`Bitflag`|
|`Callback`|`callback`|`CallBack`|
|`Canceled`|`canceled`|`Cancelled`|
|`DoNot`|`doNot`|`Don't`|
|`Email`|`email`|`EMail`|
|`Endpoint`|`endpoint`|`EndPoint`|
|`FileName`|`fileName`|`Filename`|
|`Gridline`|`gridline`|`GridLine`|
|`Hashtable`|`hashtable`|`HashTable`|
|`Id`|`id`|`ID`|
|`Indexes`|`indexes`|`Indices`|
|`LogOff`|`logOff`|`LogOut`|
|`LogOn`|`logOn`|`LogIn`|
|`Metadata`|`metadata`|`MetaData, metaData`|
|`Multipanel`|`multipanel`|`MultiPanel`|
|`Multiview`|`multiview`|`MultiView`|
|`Namespace`|`namespace`|`NameSpace`|
|`Ok`|`ok`|`OK`|
|`Pi`|`pi`|`PI`|
|`Placeholder`|`placeholder`|`PlaceHolder`|
|`SignIn`|`signIn`|`SignOn`|
|`SignOut`|`signOut`|`SignOff`|
|`UserName`|`userName`|`Username`|
|`WhiteSpace`|`whiteSpace`|`Whitespace`|
|`Writable`|`writable`|`Writeable`|

## <a name="case-sensitivity"></a><span data-ttu-id="4a4ad-149">Чувствительность к регистру</span><span class="sxs-lookup"><span data-stu-id="4a4ad-149">Case Sensitivity</span></span>
 <span data-ttu-id="4a4ad-150">Языки, которые могут выполняться в среде CLR, не должны поддерживать чувствительность к регистру, хотя и некоторые.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-150">Languages that can run on the CLR are not required to support case-sensitivity, although some do.</span></span> <span data-ttu-id="4a4ad-151">Даже если ваш язык поддерживает, другие языки, которые могут получить доступ к вашей платформе, не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-151">Even if your language supports it, other languages that might access your framework do not.</span></span> <span data-ttu-id="4a4ad-152">Все интерфейсы API, доступ к которым осуществляется извне, поэтому не могут полагаться только на регистр, чтобы различать два имени в одном контексте.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-152">Any APIs that are externally accessible, therefore, cannot rely on case alone to distinguish between two names in the same context.</span></span>

 <span data-ttu-id="4a4ad-153">❌ НЕ следует рассчитывать на то, что все языки программирования чувствительны к регистру.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-153">❌ DO NOT assume that all programming languages are case sensitive.</span></span> <span data-ttu-id="4a4ad-154">Это не так.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-154">They are not.</span></span> <span data-ttu-id="4a4ad-155">Имена не могут отличаться только регистром.</span><span class="sxs-lookup"><span data-stu-id="4a4ad-155">Names cannot differ by case alone.</span></span>

 <span data-ttu-id="4a4ad-156">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="4a4ad-156">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="4a4ad-157">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="4a4ad-157">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="4a4ad-158">См. также статью</span><span class="sxs-lookup"><span data-stu-id="4a4ad-158">See also</span></span>

- [<span data-ttu-id="4a4ad-159">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="4a4ad-159">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="4a4ad-160">Рекомендации по именованию</span><span class="sxs-lookup"><span data-stu-id="4a4ad-160">Naming Guidelines</span></span>](naming-guidelines.md)

---
title: Имена сборок и библиотек DLL
description: Ознакомьтесь с рекомендациями по именованию сборок и библиотек динамической компоновки (DLL). Сборка может охватывать один или несколько файлов, но обычно она сопоставляется один к одному с библиотекой DLL.
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: de7ce3ee774d4598521d7156d0d660c3fe30154c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594482"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="f40f6-104">Имена сборок и библиотек DLL</span><span class="sxs-lookup"><span data-stu-id="f40f6-104">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="f40f6-105">Сборка — это единица развертывания и идентификации для программ управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="f40f6-105">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="f40f6-106">Хотя сборки могут охватывать один или несколько файлов, обычно сборка сопоставляет один к одному с библиотекой DLL.</span><span class="sxs-lookup"><span data-stu-id="f40f6-106">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="f40f6-107">Поэтому в этом разделе описываются только соглашения об именовании библиотек DLL, которые затем можно сопоставить с соглашениями об именовании сборок.</span><span class="sxs-lookup"><span data-stu-id="f40f6-107">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>

 <span data-ttu-id="f40f6-108">✔️ выбрать имена для библиотек DLL сборки, которые предлагают большие фрагменты функциональности, такие как System. Data.</span><span class="sxs-lookup"><span data-stu-id="f40f6-108">✔️ DO choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>

 <span data-ttu-id="f40f6-109">Имена сборок и библиотек DLL не должны соответствовать именам пространств имен, но при именовании сборок разумно следовать имени пространства имен.</span><span class="sxs-lookup"><span data-stu-id="f40f6-109">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="f40f6-110">Хорошим правилом Thumb является имя библиотеки DLL на основе общего префикса пространств имен, содержащихся в сборке.</span><span class="sxs-lookup"><span data-stu-id="f40f6-110">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="f40f6-111">Например, `MyCompany.MyTechnology.FirstFeature` `MyCompany.MyTechnology.SecondFeature` может быть вызвана сборка с двумя пространствами имен, и `MyCompany.MyTechnology.dll` .</span><span class="sxs-lookup"><span data-stu-id="f40f6-111">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>

 <span data-ttu-id="f40f6-112">✔️ Рассмотрите возможность именования библиотек DLL в соответствии со следующим шаблоном:</span><span class="sxs-lookup"><span data-stu-id="f40f6-112">✔️ CONSIDER naming DLLs according to the following pattern:</span></span>

 `<Company>.<Component>.dll`

 <span data-ttu-id="f40f6-113">где `<Component>` содержит одно или несколько предложений, разделенных точкой.</span><span class="sxs-lookup"><span data-stu-id="f40f6-113">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="f40f6-114">Пример.</span><span class="sxs-lookup"><span data-stu-id="f40f6-114">For example:</span></span>

 <span data-ttu-id="f40f6-115">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="f40f6-115">`Litware.Controls.dll`.</span></span>

 <span data-ttu-id="f40f6-116">*Части © 2005, 2009 Корпорация Майкрософт. Все права защищены.*</span><span class="sxs-lookup"><span data-stu-id="f40f6-116">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="f40f6-117">*Перепечатано с разрешения Pearson Education, Inc. из книги [Инфраструктура программных проектов. Соглашения, идиомы и шаблоны для многократно используемых библиотек .NET (2-е издание)](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619), авторы: Кржиштоф Цвалина (Krzysztof Cwalina) и Брэд Абрамс (Brad Abrams). Книга опубликована 22 октября 2008 г. издательством Addison-Wesley Professional в рамках серии, посвященной разработке для Microsoft Windows.*</span><span class="sxs-lookup"><span data-stu-id="f40f6-117">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="f40f6-118">Дополнительно</span><span class="sxs-lookup"><span data-stu-id="f40f6-118">See also</span></span>

- [<span data-ttu-id="f40f6-119">Рекомендации по проектированию платформы</span><span class="sxs-lookup"><span data-stu-id="f40f6-119">Framework Design Guidelines</span></span>](index.md)
- [<span data-ttu-id="f40f6-120">Рекомендации по именованию</span><span class="sxs-lookup"><span data-stu-id="f40f6-120">Naming Guidelines</span></span>](naming-guidelines.md)

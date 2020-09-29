---
description: -baseaddress (параметры компилятора C#)
title: -baseaddress (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /dllbase
helpviewer_keywords:
- baseaddress compiler option [C#]
- -baseaddress compiler option [C#]
- /baseaddress compiler option [C#]
ms.assetid: ce13c965-dfe4-4433-94f5-63b476e3a608
ms.openlocfilehash: 76da496f7045f12778bba273947b913be1b94e3e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196849"
---
# <a name="-baseaddress-c-compiler-options"></a><span data-ttu-id="e1f77-103">-baseaddress (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="e1f77-103">-baseaddress (C# Compiler Options)</span></span>

<span data-ttu-id="e1f77-104">Параметр **-baseaddress** позволяет указать предпочтительный базовый адрес для загрузки библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="e1f77-104">The **-baseaddress** option lets you specify the preferred base address at which to load a DLL.</span></span> <span data-ttu-id="e1f77-105">Дополнительные сведения о случаях использования этого параметра см. в [блоге Ларри Остермана (Larry Osterman)](/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).</span><span class="sxs-lookup"><span data-stu-id="e1f77-105">For more information about when and why to use this option, see [Larry Osterman's WebLog](/archive/blogs/larryosterman/why-should-i-even-bother-to-use-dlls-in-my-system).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1f77-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e1f77-106">Syntax</span></span>  
  
```console  
-baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="e1f77-107">Аргументы</span><span class="sxs-lookup"><span data-stu-id="e1f77-107">Arguments</span></span>  

 `address`  
 <span data-ttu-id="e1f77-108">Базовый адрес для библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="e1f77-108">The base address for the DLL.</span></span> <span data-ttu-id="e1f77-109">Этот адрес можно задать в десятичном, шестнадцатеричном или восьмеричном формате.</span><span class="sxs-lookup"><span data-stu-id="e1f77-109">This address can be specified as a decimal, hexadecimal, or octal number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e1f77-110">Remarks</span><span class="sxs-lookup"><span data-stu-id="e1f77-110">Remarks</span></span>  

 <span data-ttu-id="e1f77-111">Базовый адрес по умолчанию для библиотеки DLL задается в среде выполнения .NET.</span><span class="sxs-lookup"><span data-stu-id="e1f77-111">The default base address for a DLL is set by the .NET common language runtime.</span></span>  
  
 <span data-ttu-id="e1f77-112">Обратите внимание, что младшее слово этого адреса будет округляться.</span><span class="sxs-lookup"><span data-stu-id="e1f77-112">Be aware that the lower-order word in this address will be rounded.</span></span> <span data-ttu-id="e1f77-113">Например, значение 0x11110001 округляется до 0x11110000.</span><span class="sxs-lookup"><span data-stu-id="e1f77-113">For example, if you specify 0x11110001, it will be rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="e1f77-114">Чтобы завершить процесс подписи для библиотеки DLL, используйте файл SN. EXE с параметром -R.</span><span class="sxs-lookup"><span data-stu-id="e1f77-114">To complete the signing process for a DLL, use SN.EXE with the -R option.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="e1f77-115">Установка данного параметра компилятора в среде разработки Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e1f77-115">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="e1f77-116">Откройте страницу **Свойства** проекта.</span><span class="sxs-lookup"><span data-stu-id="e1f77-116">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="e1f77-117">Щелкните страницу свойств **Сборка**.</span><span class="sxs-lookup"><span data-stu-id="e1f77-117">Click the **Build** property page.</span></span>  
  
3. <span data-ttu-id="e1f77-118">Нажмите кнопку **Дополнительно** .</span><span class="sxs-lookup"><span data-stu-id="e1f77-118">Click the **Advanced** button.</span></span>  
  
4. <span data-ttu-id="e1f77-119">Измените свойство **Базовый адрес DLL**.</span><span class="sxs-lookup"><span data-stu-id="e1f77-119">Modify the **DLL Base Address** property.</span></span>  
  
     <span data-ttu-id="e1f77-120">Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span><span class="sxs-lookup"><span data-stu-id="e1f77-120">To set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.BaseAddress%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1f77-121">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e1f77-121">See also</span></span>

- <xref:System.Diagnostics.ProcessModule.BaseAddress%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e1f77-122">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="e1f77-122">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="e1f77-123">Управление свойствами проектов и решений</span><span class="sxs-lookup"><span data-stu-id="e1f77-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

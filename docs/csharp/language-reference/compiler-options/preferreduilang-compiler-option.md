---
description: -preferreduilang (параметры компилятора C#)
title: -preferreduilang (параметры компилятора C#)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: f68652e910651ab5c4184376d9eb7729303382d9
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2020
ms.locfileid: "89124855"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="0e5fc-103">-preferreduilang (параметры компилятора C#)</span><span class="sxs-lookup"><span data-stu-id="0e5fc-103">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="0e5fc-104">С помощью параметра компилятора `-preferreduilang` можно указать язык, на котором компилятор C# отображает выходные данные, например сообщения об ошибках.</span><span class="sxs-lookup"><span data-stu-id="0e5fc-104">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e5fc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e5fc-105">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="0e5fc-106">Аргументы</span><span class="sxs-lookup"><span data-stu-id="0e5fc-106">Arguments</span></span>  
 `language`  
 <span data-ttu-id="0e5fc-107">[Имя языка](/windows/desktop/Intl/language-names), который будет использоваться для вывода компилятора.</span><span class="sxs-lookup"><span data-stu-id="0e5fc-107">The [language name](/windows/desktop/Intl/language-names) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e5fc-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="0e5fc-108">Remarks</span></span>  
 <span data-ttu-id="0e5fc-109">Можно использовать параметр компилятора `-preferreduilang`, чтобы указать язык, который компилятор C# должен использовать для сообщений об ошибках и других данных вывода командной строки.</span><span class="sxs-lookup"><span data-stu-id="0e5fc-109">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="0e5fc-110">Если необходимый языковой пакет не установлен, вместо него используются языковые настройки операционной системы; ошибка не возникает.</span><span class="sxs-lookup"><span data-stu-id="0e5fc-110">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="0e5fc-111">Требования</span><span class="sxs-lookup"><span data-stu-id="0e5fc-111">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e5fc-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="0e5fc-112">See also</span></span>

- [<span data-ttu-id="0e5fc-113">Параметры компилятора C# </span><span class="sxs-lookup"><span data-stu-id="0e5fc-113">C# Compiler Options</span></span>](./index.md)

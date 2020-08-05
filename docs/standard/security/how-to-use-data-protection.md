---
title: Практическое руководство. Использование защиты данных
description: Узнайте, как использовать защиту данных путем доступа к API защиты данных (DPAPI) в .NET.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DPAPI
- encryption [.NET], data protection API
- data [.NET], decryption
- ProtectedMemory class, about ProtectedMemory class
- ProtectedData class, about ProtectedData class
- cryptography [.NET], data protection API
- data protection API [.NET]
- decryption
- data [.NET], encryption
ms.assetid: 606698b0-cb1a-42ca-beeb-0bea34205d20
ms.openlocfilehash: 263a07ddf357734e819fffdd41cdff60657adf15
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/04/2020
ms.locfileid: "87557064"
---
# <a name="how-to-use-data-protection"></a>Практическое руководство. Использование защиты данных

> [!NOTE]
> Эта статья относится к Windows.
>
> Дополнительные сведения о ASP.NET Core см. в разделе [ASP.NET Core Data Protection](/aspnet/core/security/data-protection/introduction).

.NET предоставляет доступ к API защиты данных (DPAPI), который позволяет шифровать данные с помощью информации из текущей учетной записи пользователя или компьютера.  Использование API защиты данных позволяет упростить сложную задачу явного создания и хранения криптографического ключа.  
  
Используйте класс <xref:System.Security.Cryptography.ProtectedData> для шифрования копии массива байтов. Эта функция доступна в .NET Framework, .NET Core и .NET 5.  Можно указать, что данные, зашифрованные текущей учетной записью пользователя, могут быть расшифрованы только той же учетной записью, либо можно указать, что данные, зашифрованные текущей учетной записью пользователя, могут быть расшифрованы любой учетной записью на компьютере.  Подробное описание параметров <xref:System.Security.Cryptography.ProtectedData> см. в разделе, посвященном перечислению <xref:System.Security.Cryptography.DataProtectionScope>.  
  
### <a name="to-encrypt-data-to-a-file-or-stream-using-data-protection"></a>Шифрование данных в файл или поток при помощи функции защиты данных  
  
1. Создайте случайную энтропию.  
  
2. Вызовите статический метод <xref:System.Security.Cryptography.ProtectedData.Protect%2A> во время передачи массива байтов для шифрования, энтропии и области защиты данных.  
  
3. Запишите зашифрованные данные в файл или поток.  
  
### <a name="to-decrypt-data-from-a-file-or-stream-using-data-protection"></a>Расшифровка данных из файла или потока при помощи функции защиты данных  
  
1. Считайте зашифрованные данные из файла или потока.  
  
2. Вызовите статический метод <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A> во время передачи массива байтов для расшифровки и области защиты данных.  
  
## <a name="example"></a>Пример

В следующем примере кода показаны два вида шифрования и расшифровки.  Сначала пример кода выполняет шифрование и расшифровку массива байтов в памяти.  Далее этот пример кода шифрует копию массива байтов, сохраняет его в файл, загружает данные обратно из файла и затем расшифровывает эти данные.  В примере отображаются исходные данные, зашифрованные данные и расшифрованные данные.

[!code-csharp[DPAPI-HowTO#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DPAPI-HowTO/cs/sample.cs#1)]
[!code-vb[DPAPI-HowTO#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DPAPI-HowTO/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Компиляция кода  

Этот пример компилируется и выполняется только при нацеливании на .NET Framework и выполняется в Windows.

- Включите ссылку на `System.Security.dll`.  
  
- Включите пространство имен <xref:System>, <xref:System.IO>, <xref:System.Security.Cryptography> и <xref:System.Text>.  
  
## <a name="see-also"></a>См. также раздел

- [Модель криптографии](cryptography-model.md)
- [службы шифрования](cryptographic-services.md)
- [Кросс-платформенная криптография](cross-platform-cryptography.md)
- <xref:System.Security.Cryptography.ProtectedMemory>
- <xref:System.Security.Cryptography.ProtectedData>
- [ASP.NET Core Защита данных](/aspnet/core/security/data-protection/introduction)

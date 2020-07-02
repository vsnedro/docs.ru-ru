---
ms.openlocfilehash: 5e2e8d1ec5d698d1c1649c2a0a1b4b77dbdf4022
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621408"
---
### <a name="wpf-printing-stack-update"></a>Обновления стека печати WPF

#### <a name="details"></a>Подробнее

API-интерфейсы WPF для печати, использующие <xref:System.Printing.PrintQueue?displayProperty=fullName>, теперь вызывают API пакета печати документа Windows вместо устаревшего API печати XPS. Это изменение внесено в целях повышения удобства обслуживания. Ни пользователи, ни разработчики не должны заметить какие-либо изменения в поведении или использовании API. Новый стек печати по умолчанию активируется при работе с обновлением Windows 10 Creators Update. Старый стек печати по-прежнему будет работать в предыдущих версиях Windows, как и раньше.

#### <a name="suggestion"></a>Предложение

Чтобы использовать старый стек в Windows 10 Creators Update, задайте значение <code>UseXpsOMPrinting</code> REG_DWORD в разделе реестра <code>HKEY_CURRENT_USER\Software\Microsoft\.NETFramework\Windows Presentation Foundation\Printing</code> равным <code>1</code>.

| name    | Значение       |
|:--------|:------------|
| Область   |Пограничный случай|
|Version|4.7|
|Type|Среда выполнения|

---
title: Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog
description: Узнайте, как использовать компонент SaveFileDialog для просмотра файловой системы и выбора файлов для сохранения.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- SaveFileDialog component [Windows Forms], saving files
- files [Windows Forms], saving
- OpenFile method [Windows Forms], saving files with SaveFileDialog component
ms.assetid: 02e8f409-b83f-4707-babb-e71f6b223d90
ms.openlocfilehash: cd773c3d4aa2b907eb09dd87c3fdbe138bf533bb
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904407"
---
# <a name="how-to-save-files-using-the-savefiledialog-component"></a><span data-ttu-id="5b8ca-103">Практическое руководство. Сохранение файлов с помощью компонента SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="5b8ca-103">How to: Save Files Using the SaveFileDialog Component</span></span>

<span data-ttu-id="5b8ca-104"><xref:System.Windows.Forms.SaveFileDialog>Компонент позволяет пользователям просматривать файловую систему и выбирать файлы для сохранения.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-104">The <xref:System.Windows.Forms.SaveFileDialog> component allows users to browse the file system and select files to be saved.</span></span> <span data-ttu-id="5b8ca-105">Диалоговое окно возвращает путь и имя файла, который пользователь выбрал в диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-105">The dialog box returns the path and name of the file the user has selected in the dialog box.</span></span> <span data-ttu-id="5b8ca-106">Тем не менее для фактического сохранения файла на диск необходимо написать специальный код.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-106">However, you must write the code to actually write the files to disk.</span></span>

### <a name="to-save-a-file-using-the-savefiledialog-component"></a><span data-ttu-id="5b8ca-107">Сохранение файла с помощью компонента SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="5b8ca-107">To save a file using the SaveFileDialog component</span></span>

- <span data-ttu-id="5b8ca-108">Выведите на экран диалоговое окно **Сохранить файл** и вызовите метод для сохранения файла, выбранного пользователем.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-108">Display the **Save File** dialog box and call a method to save the file selected by the user.</span></span>

  <span data-ttu-id="5b8ca-109"><xref:System.Windows.Forms.SaveFileDialog> <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> Чтобы сохранить файл, используйте метод компонента.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-109">Use the <xref:System.Windows.Forms.SaveFileDialog> component's <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="5b8ca-110">Этот метод предоставляет объект, который <xref:System.IO.Stream> можно записать в.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-110">This method gives you a <xref:System.IO.Stream> object you can write to.</span></span>

  <span data-ttu-id="5b8ca-111">В приведенном ниже примере <xref:System.Windows.Forms.DialogResult> свойство используется для получения имени файла, а <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> метод — для сохранения файла.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-111">The example below uses the <xref:System.Windows.Forms.DialogResult> property to get the name of the file, and the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to save the file.</span></span> <span data-ttu-id="5b8ca-112"><xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A>Метод предоставляет поток для записи файла.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-112">The <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> method gives you a stream to write the file to.</span></span>

  <span data-ttu-id="5b8ca-113">В приведенном ниже примере имеется <xref:System.Windows.Forms.Button> элемент управления с назначенным ему изображением.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-113">In the example below, there is a <xref:System.Windows.Forms.Button> control with an image assigned to it.</span></span> <span data-ttu-id="5b8ca-114">При нажатии кнопки создается <xref:System.Windows.Forms.SaveFileDialog> экземпляр компонента с фильтром, который разрешает файлы типа. gif,. JPEG и. bmp.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-114">When you click the button, a <xref:System.Windows.Forms.SaveFileDialog> component is instantiated with a filter that allows files of type .gif, .jpeg, and .bmp.</span></span> <span data-ttu-id="5b8ca-115">При выборе файла такого типа в диалоговом окне "Сохранить файл" изображение кнопки сохраняется.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-115">If a file of this type is selected in the Save File dialog box, the button's image is saved.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="5b8ca-116">Чтобы получить или задать <xref:System.Windows.Forms.FileDialog.FileName%2A> свойство, сборке требуется уровень привилегий, предоставляемый <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> классом.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-116">To get or set the <xref:System.Windows.Forms.FileDialog.FileName%2A> property, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermission?displayProperty=nameWithType> class.</span></span> <span data-ttu-id="5b8ca-117">Если процесс выполняется в контексте с частичным доверием, он может сгенерировать исключение из-за недостатка привилегий.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-117">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="5b8ca-118">Дополнительные сведения см. в разделе [Code Access Security Basics](../../misc/code-access-security-basics.md).</span><span class="sxs-lookup"><span data-stu-id="5b8ca-118">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

  <span data-ttu-id="5b8ca-119">В примере предполагается, что в форме есть <xref:System.Windows.Forms.Button> элемент управления со <xref:System.Windows.Forms.ButtonBase.Image%2A> свойством, для которого задано значение файла типа. gif,. JPEG или. bmp.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-119">The example assumes your form has a <xref:System.Windows.Forms.Button> control with its <xref:System.Windows.Forms.ButtonBase.Image%2A> property set to a file of type .gif, .jpeg, or .bmp.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5b8ca-120"><xref:System.Windows.Forms.FileDialog> <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> Свойство класса (из-за наследования является частью <xref:System.Windows.Forms.SaveFileDialog> класса) использует индекс, отсчитываемый от единицы.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-120">The <xref:System.Windows.Forms.FileDialog> class's <xref:System.Windows.Forms.FileDialog.FilterIndex%2A> property (which, due to inheritance, is part of the <xref:System.Windows.Forms.SaveFileDialog> class) uses a one-based index.</span></span> <span data-ttu-id="5b8ca-121">Это важно при написании кода для сохранения данных в определенном формате (например, в формате обычного текста или двоичном формате).</span><span class="sxs-lookup"><span data-stu-id="5b8ca-121">This is important if you are writing code to save data in a specific format (for example, saving a file in plain text versus binary format).</span></span> <span data-ttu-id="5b8ca-122">Это свойство представлено в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-122">This property is featured in the example below.</span></span>

  ```vb
  Private Sub Button2_Click(ByVal sender As System.Object, _
  ByVal e As System.EventArgs) Handles Button2.Click
      ' Displays a SaveFileDialog so the user can save the Image
      ' assigned to Button2.
      Dim saveFileDialog1 As New SaveFileDialog()
      saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif"
      saveFileDialog1.Title = "Save an Image File"
      saveFileDialog1.ShowDialog()

      ' If the file name is not an empty string open it for saving.
      If saveFileDialog1.FileName <> "" Then
        ' Saves the Image via a FileStream created by the OpenFile method.
        Dim fs As System.IO.FileStream = Ctype _
            (saveFileDialog1.OpenFile(), System.IO.FileStream)
        ' Saves the Image in the appropriate ImageFormat based upon the
        ' file type selected in the dialog box.
        ' NOTE that the FilterIndex property is one-based.
        Select Case saveFileDialog1.FilterIndex
            Case 1
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Jpeg)

            Case 2
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Bmp)

            Case 3
              Me.button2.Image.Save(fs, _
                  System.Drawing.Imaging.ImageFormat.Gif)
          End Select

          fs.Close()
      End If
  End Sub
  ```

  ```csharp
  private void button2_Click(object sender, System.EventArgs e)
  {
      // Displays a SaveFileDialog so the user can save the Image
      // assigned to Button2.
      SaveFileDialog saveFileDialog1 = new SaveFileDialog();
      saveFileDialog1.Filter = "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";
      saveFileDialog1.Title = "Save an Image File";
      saveFileDialog1.ShowDialog();

      // If the file name is not an empty string open it for saving.
      if(saveFileDialog1.FileName != "")
      {
        // Saves the Image via a FileStream created by the OpenFile method.
        System.IO.FileStream fs =
            (System.IO.FileStream)saveFileDialog1.OpenFile();
        // Saves the Image in the appropriate ImageFormat based upon the
        // File type selected in the dialog box.
        // NOTE that the FilterIndex property is one-based.
        switch(saveFileDialog1.FilterIndex)
        {
            case 1 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Jpeg);
            break;

            case 2 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Bmp);
            break;

            case 3 :
            this.button2.Image.Save(fs,
              System.Drawing.Imaging.ImageFormat.Gif);
            break;
        }

      fs.Close();
      }
  }
  ```

  ```cpp
  private:
      System::Void button2_Click(System::Object ^ sender,
        System::EventArgs ^ e)
      {
        // Displays a SaveFileDialog so the user can save the Image
        // assigned to Button2.
        SaveFileDialog ^ saveFileDialog1 = new SaveFileDialog();
        saveFileDialog1->Filter =
            "JPeg Image|*.jpg|Bitmap Image|*.bmp|Gif Image|*.gif";
        saveFileDialog1->Title = "Save an Image File";
        saveFileDialog1->ShowDialog();
        // If the file name is not an empty string, open it for saving.
        if(saveFileDialog1->FileName != "")
        {
            // Saves the Image through a FileStream created by
            // the OpenFile method.
            System::IO::FileStream ^ fs =
              safe_cast\<System::IO::FileStream*>(
              saveFileDialog1->OpenFile());
            // Saves the Image in the appropriate ImageFormat based on
            // the file type selected in the dialog box.
            // Note that the FilterIndex property is one based.
            switch(saveFileDialog1->FilterIndex)
            {
              case 1 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Jpeg);
                  break;
              case 2 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Bmp);
                  break;
              case 3 :
                  this->button2->Image->Save(fs,
                    System::Drawing::Imaging::ImageFormat::Gif);
                  break;
            }
        fs->Close();
        }
      }
  ```

  <span data-ttu-id="5b8ca-123">(Visual C# и Visual C++) Поместите следующий код в конструктор формы для регистрации обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-123">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>

  ```csharp
  this.button2.Click += new System.EventHandler(this.button2_Click);
  ```

  ```cpp
  this->button2->Click += gcnew
      System::EventHandler(this, &Form1::button2_Click);
  ```

  <span data-ttu-id="5b8ca-124">Дополнительные сведения о записи файловых потоков см. в статьях <xref:System.IO.FileStream.BeginWrite%2A> и <xref:System.IO.FileStream.Write%2A> .</span><span class="sxs-lookup"><span data-stu-id="5b8ca-124">For more information about writing file streams, see <xref:System.IO.FileStream.BeginWrite%2A> and <xref:System.IO.FileStream.Write%2A>.</span></span>

  > [!NOTE]
  > <span data-ttu-id="5b8ca-125">Некоторые элементы управления, такие как <xref:System.Windows.Forms.RichTextBox> элемент управления, имеют возможность сохранять файлы.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-125">Certain controls, such as the <xref:System.Windows.Forms.RichTextBox> control, have the ability to save files.</span></span>

## <a name="see-also"></a><span data-ttu-id="5b8ca-126">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="5b8ca-126">See also</span></span>

- <xref:System.Windows.Forms.SaveFileDialog>
- [<span data-ttu-id="5b8ca-127">Компонент SaveFileDialog</span><span class="sxs-lookup"><span data-stu-id="5b8ca-127">SaveFileDialog Component</span></span>](savefiledialog-component-windows-forms.md)

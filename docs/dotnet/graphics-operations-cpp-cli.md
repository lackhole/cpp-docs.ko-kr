---
title: 그래픽 작업(C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- GDI+ [C++]
- .NET Framework [C++], graphics
- images [C++], .NET Framework and
- GDI+ [C++], about graphics operations
- graphics [C++], .NET Framework and
- GDI+ [C++], displaying images
- graphics [C++], displaying images
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
- GDI+ [C++], rotating images
- graphics [C++], rotating images
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: bba27228-b9b3-4c9c-b31c-a04b76702a95
ms.openlocfilehash: c7c6d62eb4059069e6e266544ce6323c63dd15c0
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746281"
---
# <a name="graphics-operations-ccli"></a>그래픽 작업(C++/CLI)

Windows SDK를 사용 하 여 이미지 조작을 보여 줍니다.

다음 항목의 사용을 보여 줍니다.는 <xref:System.Drawing.Image?displayProperty=fullName> 이미지 조작을 수행 하는 클래스입니다.

## <a name="display"></a> .NET Framework로 이미지 표시

다음 코드 예제에서는 수정 OnPaint 이벤트 처리기에 대 한 포인터를 검색 하는 <xref:System.Drawing.Graphics> 기본 폼에 대 한 개체입니다. <xref:System.Windows.Forms.Form.OnPaint%2A> 함수 대부분 Visual Studio 응용 프로그램 마법사를 사용 하 여 만든 Windows Forms 응용 프로그램을 위한 것입니다.

이미지 표시 됩니다는 <xref:System.Drawing.Image> 클래스입니다. 이미지 데이터를 사용 하 여.jpg 파일에서 로드 되는 <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> 메서드. 폼에 이미지를 그릴, 전에 폼 이미지에 맞게 크기가 조정 됩니다. 이미지의 그리기 수행 되는 <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> 메서드.

합니다 <xref:System.Drawing.Graphics> 하 고 <xref:System.Drawing.Image> 클래스는 모두를 <xref:System.Drawing?displayProperty=fullName> 네임 스페이스입니다.

### <a name="example"></a>예제

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;

protected:
virtual Void Form1::OnPaint(PaintEventArgs^ pe) override
{
    Graphics^ g = pe->Graphics;
    Image^ image = Image::FromFile("SampleImage.jpg");
    Form::ClientSize = image->Size;
    g->DrawImage( image, 0, 0, image->Size.Width, image->Size.Height );
}
```

## <a name="draw"></a> .NET Framework로 도형 그리기

다음 코드 예제에서는 합니다 <xref:System.Drawing.Graphics> 수정 하는 클래스를 <xref:System.Windows.Forms.Form.OnPaint%2A> 이벤트 처리기에 대 한 포인터를 검색 하는 <xref:System.Drawing.Graphics> 기본 폼에 대 한 개체입니다. 이 포인터는 다음 폼의 배경색을 설정 하 고 줄 및 사용 하 여 호를 그릴 하는 데 사용 됩니다 합니다 <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> 고 <xref:System.Drawing.Graphics.DrawArc%2A> 메서드.

### <a name="example"></a>예제

```cpp
#using <system.drawing.dll>
using namespace System;
using namespace System::Drawing;
// ...
protected:
virtual Void Form1::OnPaint(PaintEventArgs^ pe ) override
{
   Graphics^ g = pe->Graphics;
   g->Clear(Color::AntiqueWhite);

   Rectangle rect = Form::ClientRectangle;
   Rectangle smallRect;
   smallRect.X = rect.X + rect.Width / 4;
   smallRect.Y = rect.Y + rect.Height / 4;
   smallRect.Width = rect.Width / 2;
   smallRect.Height = rect.Height / 2;

   Pen^ redPen = gcnew Pen(Color::Red);
   redPen->Width = 4;
   g->DrawLine(redPen, 0, 0, rect.Width, rect.Height);

   Pen^ bluePen = gcnew Pen(Color::Blue);
   bluePen->Width = 10;
   g->DrawArc( bluePen, smallRect, 90, 270 );
}
```

## <a name="rotate"></a> .NET Framework로 이미지 회전

다음 코드 예제에서는 <xref:System.Drawing.Image?displayProperty=fullName> 클래스를 디스크에서 이미지를 로드, 90도 회전 및 새.jpg 파일로 저장 합니다.

### <a name="example"></a>예제

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;

int main()
{
   Image^ image = Image::FromFile("SampleImage.jpg");
   image->RotateFlip( RotateFlipType::Rotate90FlipNone );
   image->Save("SampleImage_rotated.jpg");
   return 0;
}
```

## <a name="convert"></a> .NET Framework로 이미지 파일 형식 변환

다음 코드 예제는 <xref:System.Drawing.Image?displayProperty=fullName> 클래스 및 <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> 변환 하 고 이미지 파일을 저장 하는 데 사용 하는 열거형입니다. 다음 코드는.jpg 파일에서 이미지를 로드 하 고.gif 및.bmp 파일 형식으로 저장 합니다.

### <a name="example"></a>예제

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;
using namespace System::Drawing::Imaging;

int main()
{
   Image^ image = Image::FromFile("SampleImage.jpg");
   image->Save("SampleImage.png", ImageFormat::Png);
   image->Save("SampleImage.bmp", ImageFormat::Bmp);

   return 0;
}
```

## <a name="related-sections"></a>관련 단원

[그래픽 프로그래밍 시작](/dotnet/framework/winforms/advanced/getting-started-with-graphics-programming)

[GDI + 관리 코드 정보](/dotnet/framework/winforms/advanced/about-gdi-managed-code)

## <a name="see-also"></a>참고자료

[C++/CLI를 사용한 .NET 프로그래밍(Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

<xref:System.Drawing>

---
title: '방법: 전역 예외 처리기 정의 및 설치'
ms.date: 11/04/2016
helpviewer_keywords:
- handlers, global
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
ms.openlocfilehash: d1b8452d19172bf16817c36032189accfd855539
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58777210"
---
# <a name="how-to-define-and-install-a-global-exception-handler"></a>방법: 전역 예외 처리기 정의 및 설치

다음 코드 예제에서는 어떻게 처리 되지 않은 예외 캡처할 수 있습니다. 예제에서는 양식에 단추를 누르면 수행 null 참조 예외를 throw 합니다. 이 기능은 일반적인 코드 오류를 나타냅니다. Main 함수에 의해 설치 된 응용 프로그램 수준의 예외 처리기에서 결과 예외가 검색 되었습니다.

이렇게 하려면 대리자를 바인딩하여는 <xref:System.Windows.Forms.Application.ThreadException> 이벤트입니다. 이 경우 후속 예외도 보내집니다는 `App::OnUnhandled` 메서드.

## <a name="example"></a>예제

```
// global_exception_handler.cpp
// compile with: /clr
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Threading;
using namespace System::Drawing;
using namespace System::Windows::Forms;

ref class MyForm : public Form
{
   Button^ b;
public:
   MyForm( )
   {
      b = gcnew Button( );
      b->Text = "Do Null Access";
      b->Size = Drawing::Size(150, 30);
      b->Click += gcnew EventHandler(this, &MyForm::OnClick);
      Controls->Add(b);
   }
   void OnClick(Object^ sender, EventArgs^ args)
   {
      // do something illegal, like call through a null pointer...
      Object^ o = nullptr;
      o->ToString( );
   }
};

ref class App
{
public:
   static void OnUnhandled(Object^ sender, ThreadExceptionEventArgs^ e)
   {
      MessageBox::Show(e->Exception->Message, "Global Exeception");
      Application::ExitThread( );
   }
};

int main()
{
   Application::ThreadException += gcnew
      ThreadExceptionEventHandler(App::OnUnhandled);

   MyForm^ form = gcnew MyForm( );
   Application::Run(form);
}
```

## <a name="see-also"></a>참고자료

[예외 처리](../extensions/exception-handling-cpp-component-extensions.md)

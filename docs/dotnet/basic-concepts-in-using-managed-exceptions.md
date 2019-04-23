---
title: 관리되는 예외 사용의 기본 개념
ms.date: 11/04/2016
helpviewer_keywords:
- try-catch exception handling, managed applications
- __finally keyword, managed exceptions
- exceptions, managed
- try-catch exception handling
- catch blocks
- throwing exceptions, managed exceptions
- Visual C++, handling managed exceptions
ms.assetid: 40ce8931-1ecc-491a-815f-733b23fcba35
ms.openlocfilehash: e2aed98d9131b3d7b96cdc3e3297823d69d0ad38
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781538"
---
# <a name="basic-concepts-in-using-managed-exceptions"></a>관리되는 예외 사용의 기본 개념

이 항목에서는 관리 되는 응용 프로그램의 예외 처리를 설명 합니다. 즉, 응용 프로그램을 사용 하 여 컴파일된 합니다 **/clr** 컴파일러 옵션입니다.

## <a name="in-this-topic"></a>항목 내용

- [/Clr에서 예외를 throw합니다.](#vcconbasicconceptsinusingmanagedexceptionsanchor1)

- [Try/Catch 블록 CLR 확장](#vcconbasicconceptsinusingmanagedexceptionsanchor2)

## <a name="remarks"></a>설명

로 컴파일하는 경우는 **/clr** 옵션을 표준 뿐만 아니라 CLR 예외를 처리할 수 있습니다 <xref:System.Exception> 클래스 CLR 예외 처리를 위한 많은 유용한 메서드를 제공 하 고 사용자 정의 예외에 대 한 기본 클래스로 사용 하는 것이 좋습니다. 클래스입니다.

인터페이스에서 파생 된 예외 형식을 catch 할에서 지원 되지 않습니다 **/clr**합니다. 또한 공용 언어 런타임 허용 하지 않습니다 스택 오버플로 예외를 catch 합니다. 스택 오버플로 예외는 프로세스를 종료 합니다.

관리 및 관리 되지 않는 응용 프로그램에서 예외 처리의 차이점에 대 한 자세한 내용은 참조 하세요. [차이점 예외 처리 동작에서 Managed extensions for C++ ](../dotnet/differences-in-exception-handling-behavior-under-clr.md)합니다.

##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor1"></a> /Clr에서 예외를 throw합니다.

C++ throw 식 CLR 형식에 대 한 핸들을 throw 하도록 확장 되었습니다. 다음 예제에서는 사용자 지정 예외 형식을 만들고 해당 형식의 인스턴스가 throw 됩니다.

```
// clr_exception_handling.cpp
// compile with: /clr /c
ref struct MyStruct: public System::Exception {
public:
   int i;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   throw pMyStruct;
}
```

Throw 하기 전에 값 형식에 넣을 해야 합니다.

```
// clr_exception_handling_2.cpp
// compile with: /clr /c
value struct MyValueStruct {
   int i;
};

void GlobalFunction() {
   MyValueStruct v = {11};
   throw (MyValueStruct ^)v;
}
```

##  <a name="vcconbasicconceptsinusingmanagedexceptionsanchor2"></a> Try/Catch 블록 CLR 확장

동일 **시도**/**catch** , CLR 및 네이티브 예외를 catch 하기 위한 블록 구조를 사용할 수 있습니다.

```
// clr_exception_handling_3.cpp
// compile with: /clr
using namespace System;
ref struct MyStruct : public Exception {
public:
   int i;
};

struct CMyClass {
public:
   double d;
};

void GlobalFunction() {
   MyStruct^ pMyStruct = gcnew MyStruct;
   pMyStruct->i = 11;
   throw pMyStruct;
}

void GlobalFunction2() {
   CMyClass c = {2.0};
   throw c;
}

int main() {
   for ( int i = 1; i >= 0; --i ) {
      try {
         if ( i == 1 )
            GlobalFunction2();
         if ( i == 0 )
            GlobalFunction();
      }
      catch ( CMyClass& catchC ) {
         Console::WriteLine( "In 'catch(CMyClass& catchC)'" );
         Console::WriteLine( catchC.d );
      }
      catch ( MyStruct^ catchException ) {
         Console::WriteLine( "In 'catch(MyStruct^ catchException)'" );
         Console::WriteLine( catchException->i );
      }
   }
}
```

### <a name="output"></a>출력

```
In 'catch(CMyClass& catchC)'
2
In 'catch(MyStruct^ catchException)'
11
```

### <a name="order-of-unwinding-for-c-objects"></a>해제 순서 C++ 개체

에 대해 발생 해제 C++ 소멸자가 throw 함수 사이의 처리 함수 런타임 스택을에 있을 수 있는 개체입니다. 힙에 할당 된 CLR 형식 때문에 해제 해도에 적용 되지 않습니다.

Throw 된 예외에 대 한 이벤트의 순서는 다음과 같습니다.

1. 런타임에서 나 SEH를 적절 한 catch 절에 대해 원하는 스택을 예외를 catch 하 SEH에 대 한 필터를 제외 하 고 있습니다. Catch 절 어휘 순서로 먼저 검색 되 고 동적으로 아래로 호출 스택.

1. 올바른 처리기 발견 되 면 해당 지점에는 스택 해제 됩니다. 스택의 각 함수 호출에 대 한 해당 로컬 개체는 소멸 됩니다 및 __finally 블록에서에서 실행 되는, 가장 바깥쪽 중첩 합니다.

1. 스택의 스택이 해제 되 면 catch 절이 실행 됩니다.

### <a name="catching-unmanaged-types"></a>관리 되지 않는 형식을 catch합니다.

형식의 예외를 사용 하 여 래핑되는 관리 되지 않는 개체 유형을 throw 되 면 <xref:System.Runtime.InteropServices.SEHException>합니다. 적절 한 검색 하는 경우 **catch** 절을 두 가지 방법이 있습니다.

- 경우는 네이티브 C++ 형식이 발견 될, 예외는 래핑 해제 되 고 해당 형식과 비교 합니다. 이 비교는 네이티브를 사용 하면 C++ 를 일반적인 방법으로 발견할 수 있는 형식입니다.

- 그러나 경우에 **catch** 형식의 절 **SEHException** 또는 해당 기본 클래스 중 하나를 먼저 검사, 절은 예외를 가로챕니다. 따라서 두어야 catch 하는 모든 catch 절 네이티브 C++ 모든 CLR 형식의 절을 catch 하기 전에 먼저 형식입니다.

다음 사항에 유의하십시오.

```
catch(Object^)
```

및

```
catch(...)
```

SEH 예외를 포함 한 모든 throw 된 형식이 모두 catch 합니다.

관리 되지 않는 형식 catch(Object^)에서 포착 되, throw 된 개체를 삭제 하지 않습니다.

관리 되지 않은 예외를 throw 또는 catch 할 때 사용 하는 것이 좋습니다 합니다 [/EHsc](../build/reference/eh-exception-handling-model.md) 대신 컴파일러 옵션 **/EHs** 하거나 **/EHa**합니다.

## <a name="see-also"></a>참고자료

[예외 처리](../extensions/exception-handling-cpp-component-extensions.md)<br/>
[safe_cast](../extensions/safe-cast-cpp-component-extensions.md)<br/>
[예외 처리](../cpp/exception-handling-in-visual-cpp.md)

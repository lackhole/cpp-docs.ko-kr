---
title: '방법: C + 열거형 정의 및 사용 + CLI'
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: 9787b7b96f83b2926c65209254c88eb56fe1a8ab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387385"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>방법: C + 열거형 정의 및 사용 + CLI

이 항목에서는 열거형에 설명 C++/CLI입니다.

## <a name="specifying-the-underlying-type-of-an-enum"></a>열거형의 내부 형식 지정

기본적으로 기본 유형의 열거형은 `int`합니다.  그러나 형식 또는 부호 없는 형식의 수를 지정할 수 있습니다 `int`, `short`, `long`합니다 `__int32`, 또는 `__int64`합니다.  사용할 수도 있습니다 `char`합니다.

```
// mcppv2_enum_3.cpp
// compile with: /clr
public enum class day_char : char {sun, mon, tue, wed, thu, fri, sat};

int main() {
   // fully qualified names, enumerator not injected into scope
   day_char d = day_char::sun, e = day_char::mon;
   System::Console::WriteLine(d);
   char f = (char)d;
   System::Console::WriteLine(f);
   f = (char)e;
   System::Console::WriteLine(f);
   e = day_char::tue;
   f = (char)e;
   System::Console::WriteLine(f);
}
```

**출력**

```Output
sun
0
1
2
```

## <a name="how-to-convert-between-managed-and-standard-enumerations"></a>관리 및 표준 열거형 간에 변환 하는 방법

열거형과 정수 계열 형식; 사이 표준 변환이 캐스트가 필요합니다.

```
// mcppv2_enum_4.cpp
// compile with: /clr
enum class day {sun, mon, tue, wed, thu, fri, sat};
enum {sun, mon, tue, wed, thu, fri, sat} day2; // unnamed std enum

int main() {
   day a = day::sun;
   day2 = sun;
   if ((int)a == day2)
   // or...
   // if (a == (day)day2)
      System::Console::WriteLine("a and day2 are the same");
   else
      System::Console::WriteLine("a and day2 are not the same");
}
```

**출력**

```Output
a and day2 are the same
```

## <a name="operators-and-enums"></a>연산자 및 열거형

다음 연산자는 C + 열거형을 사용할 + CLI:

|연산자|
|--------------|
|== != \< > \<= >=|
|+ -|
|&#124; ^ & ~|
|++ --|
|sizeof|

연산자 &#124; ^ & ~ + +-정수 계열 형식에 bool을 포함 하지 않는 기본 열거형에 대해서만 정의 됩니다.  두 피연산자의 열거형 형식 이어야 합니다.

컴파일러는 정적 또는 동적을 확인 하지 않고 결과 enum 작업의 열거형의 유효한 열거자의 범위에 없는 값을 작업이 될 수 있습니다.

> [!NOTE]
>  C + + 11에서 관리 되는 enum 클래스와 크게 다르지는 비관리 코드에서 enum 클래스 유형을 소개 C++/CLI입니다. C + + 11 열거형 클래스 형식이에서 관리 되는 열거형 클래스 형식으로 동일한 연산자를 지원 하지 않습니다, 특히 C++/CLI, 및 C++CLI 소스 코드 해야 제공 관리 되는 열거형의 액세스 가능성 한정자는 클래스 선언에서 구별 하기 위해 (C + + 11)를 관리 되지 않는 열거형 클래스 선언 합니다. Enum 클래스에 대 한 자세한 내용은 C++/CLI, C++/CX 및 C + + 11 참조 [enum 클래스](../extensions/enum-class-cpp-component-extensions.md)합니다.

```
// mcppv2_enum_5.cpp
// compile with: /clr
private enum class E { a, b } e, mask;
int main() {
   if ( e & mask )   // C2451 no E->bool conversion
      ;

   if ( ( e & mask ) != 0 )   // C3063 no operator!= (E, int)
      ;

   if ( ( e & mask ) != E() )   // OK
      ;
}
```

```
// mcppv2_enum_6.cpp
// compile with: /clr
private enum class day : int {sun, mon};
enum : bool {sun = true, mon = false} day2;

int main() {
   day a = day::sun, b = day::mon;
   day2 = sun;

   System::Console::WriteLine(sizeof(a));
   System::Console::WriteLine(sizeof(day2));
   a++;
   System::Console::WriteLine(a == b);
}
```

**출력**

```Output
4
1
True
```

## <a name="see-also"></a>참고자료

[Enum 클래스](../extensions/enum-class-cpp-component-extensions.md)

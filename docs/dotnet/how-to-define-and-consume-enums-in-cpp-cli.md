---
title: '방법: C + 열거형 정의 및 사용 + CLI'
ms.date: 11/04/2016
helpviewer_keywords:
- enum class, specifying underlying types
ms.assetid: df8f2b91-b9d2-4fab-9be4-b1d58b8bc570
ms.openlocfilehash: 0252c4b64690f6a2fb0fd97b97841fe45fcce244
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751455"
---
# <a name="how-to-define-and-consume-enums-in-ccli"></a>방법: C + 열거형 정의 및 사용 + CLI

이 항목에서는 설명 열거형 C + + /cli CLI입니다.

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
>  C + + 11에서는 C + 관리 되는 enum 클래스와 크게 다르지는 비관리 코드에서 enum 클래스 형식이 도입 되었습니다. + CLI입니다. 특히 C + + 11 열거형 클래스 형식이 연산자 지원 하지 않습니다는 동일한 관리 되는 열거형 클래스 형식으로 C + + /cli CLI 및 C + + 소스 코드 제공 해야 관리 되는 열거형의 액세스 가능성 한정자는 클래스 선언 비관리 (c + +에서 구별 하기 위해 11) 열거형 클래스 선언입니다. C + enum 클래스에 대 한 자세한 내용은 + CLI, C + + /CX 및 C + + 11 참조 [enum 클래스](../windows/enum-class-cpp-component-extensions.md)합니다.

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

[enum 클래스](../windows/enum-class-cpp-component-extensions.md)

---
title: C++ 비트 필드
ms.date: 11/19/2018
helpviewer_keywords:
- bitfields [C++]
- fields [C++], bit
- bit fields
ms.assetid: 6f4b62e3-cc1d-4e5d-bf34-05904104f71a
ms.openlocfilehash: 747920378472cc091928a080e303a0543e287aaa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154719"
---
# <a name="c-bit-fields"></a>C++ 비트 필드

클래스와 구조체는 정수 형식보다 작은 스토리지 공간을 차지하는 멤버를 포함할 수 있습니다. 이러한 멤버는 비트 필드로 지정됩니다. 비트 필드에 대 한 구문을 *멤버 선언 자* 사양 따릅니다.

## <a name="syntax"></a>구문

*declarator* **:** *constant-expression*

## <a name="remarks"></a>설명

(옵션) *declarator* 사용 되는 멤버는 프로그램에 액세스 하는 이름입니다. 정수 형식(열거형 형식 포함)이어야 합니다. 합니다 *상수-식* 구조에서 멤버가 차지 하는 비트 수를 지정 합니다. 익명 비트 필드, 식별자가 없는 비트 필드 멤버를 안쪽 여백에 사용할 수 있습니다.

> [!NOTE]
> 두께가 0의 명명 되지 않은 비트 필드는 다음 다음 비트 필드의 맞춤을 강제로 **형식** 경계, 여기서 **형식** 유형 멤버입니다.

다음 예제에서는 비트 필드가 포함된 구조체를 선언합니다.

```cpp
// bit_fields1.cpp
// compile with: /LD
struct Date {
   unsigned short nWeekDay  : 3;    // 0..7   (3 bits)
   unsigned short nMonthDay : 6;    // 0..31  (6 bits)
   unsigned short nMonth    : 5;    // 0..12  (5 bits)
   unsigned short nYear     : 8;    // 0..100 (8 bits)
};
```

다음 그림에서는 `Date` 형식 개체의 개념적 메모리 레이아웃을 보여 줍니다.

![날짜 개체의 메모리 레이아웃](../cpp/media/vc38uq1.png "날짜 개체의 메모리 레이아웃") <br/>
날짜 개체의 메모리 레이아웃

사실은 `nYear` 길이가 8 비트 이며 선언 된 형식의 단어 경계를 벗어납니다 **부호 없는** **짧은**합니다. 따라서 새의 시작 부분에서 시작 됩니다 **unsigned** **짧은**합니다. 모든 비트 필드가 기본 형식의 한 개체에 맞아야 할 필요는 없습니다. 선언에서 요청된 비트 수에 따라 새 스토리지 단위가 할당됩니다.

**Microsoft 전용**

비트 필드로 선언되는 데이터의 순서는 위의 그림에 나온 것처럼 낮은 비트에서 높은 비트의 순서입니다.

**Microsoft 전용 종료**

다음 예제와 같이 구조체 선언에 길이가 0인 명명되지 않은 필드가 포함된 경우

```cpp
// bit_fields2.cpp
// compile with: /LD
struct Date {
   unsigned nWeekDay  : 3;    // 0..7   (3 bits)
   unsigned nMonthDay : 6;    // 0..31  (6 bits)
   unsigned           : 0;    // Force alignment to next boundary.
   unsigned nMonth    : 5;    // 0..12  (5 bits)
   unsigned nYear     : 8;    // 0..100 (8 bits)
};
```

그런 다음 메모리 레이아웃은 다음 그림에 나와 있는 것 처럼:

![0 사용 하 여 날짜 개체의 레이아웃&#45;비트 필드 길이](../cpp/media/vc38uq2.png "0 사용 하 여 날짜의 레이아웃 개체&#45;비트 필드 길이") <br/>
길이가 0인 비트 필드가 있는 날짜 개체의 레이아웃

비트 필드의 내부 형식에 설명 된 대로 정수 계열 형식 이어야 합니다 [기본 형식](../cpp/fundamental-types-cpp.md)합니다.

경우에 대 한 참조 형식에 대 한 이니셜라이저 `const T&` 이 형식의 비트 필드에 대 한 참조는 lvalue `T`, 참조에 바인딩되지 않은 비트 필드 직접. 대신 참조는 비트 필드의 값을 보유할 초기화 임시에 바인딩되어 있습니다.

## <a name="restrictions-on-bit-fields"></a>비트 필드에 대한 제한

비트 필드에 대한 잘못된 연산은 다음과 같습니다.

- 비트 필드의 주소 가져오기

- 초기화가 아닌**const** 비트 필드를 사용 하 여 참조 합니다.

## <a name="see-also"></a>참고자료

[클래스 및 구조체(C++)](../cpp/classes-and-structs-cpp.md)
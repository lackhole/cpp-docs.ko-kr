---
title: 특수 멤버 함수
ms.date: 12/06/2016
helpviewer_keywords:
- special member functions [C++]
- constructors [C++]
- destructors [C++]
- copy operators [C++]
- move operators [C++]
- assignment operators [C++]
ms.assetid: 017d6817-b012-44f0-b153-f3076c251ea7
ms.openlocfilehash: 3b26628fd18749bd19819fe787888fd3264a79d1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62330982"
---
# <a name="special-member-functions"></a>특수 멤버 함수

합니다 *특수 멤버 함수* 클래스 (또는 구조체) 멤버 함수는 특정 경우에 컴파일러를 자동으로 생성 하면 됩니다. 이러한 함수는 합니다 [기본 생성자](constructors-cpp.md#default_constructors)의 [소멸자](destructors-cpp.md)의 [복사 생성자 및 복사 할당 연산자](copy-constructors-and-copy-assignment-operators-cpp.md), 및 [이동 생성자 및 이동 할당 연산자](move-constructors-and-move-assignment-operators-cpp.md)합니다. 클래스는 하나 이상의 특수 멤버 함수를 정의 하지 않으면, 다음 컴파일러 있습니다 암시적으로 선언 하 고 사용 되는 함수를 정의 합니다. 컴파일러에서 생성 된 구현이 호출 되는 *기본* 특수 멤버 함수입니다. 컴파일러는 필요 하지 않은 경우 함수를 생성 하지 않습니다.

사용 하 여 기본 특수 멤버 함수를 명시적으로 선언할 수는 **= default** 키워드입니다. 이 컴파일러에서 필요한 경우에 동일한 방식으로 함수에서 선언 되지 않은 것 처럼 함수를 정의 합니다.

일부 경우에 컴파일러 생성할 수 있습니다 *삭제* 정의 되 고 따라서 하지 호출 가능 하지 않은 특수 멤버 함수입니다. 이 클래스에는 특정 특수 멤버 함수에 대 한 호출 적합 하지 않습니다, 클래스의 다른 속성을 지정 하는 경우에 발생할 수 있습니다. 특수 멤버 함수의 자동 생성을 명시적으로 방지 하려면 선언할 수 있습니다 사용 하 여 삭제 합니다 **= 삭제** 키워드입니다.

컴파일러에서 생성 된 *기본 생성자*, 다른 생성자를 선언 하지 하는 경우에 인수를 사용 하는 생성자입니다. 매개 변수를 사용 하는 생성자를 선언한 경우 기본 생성자를 호출 하는 코드 컴파일러에서 오류 메시지를 생성 합니다. 컴파일러에서 생성 된 기본 생성자는 member-wise 간단한 수행 [기본 초기화](initializers.md#default_initialization) 개체입니다. 기본 초기화 되지 않은 상태에서 모든 멤버 변수를 유지합니다.

기본 소멸자는 개체의 member-wise 소멸을 수행합니다. 가상 기본 클래스 소멸자는 경우에 가상 됩니다.

기본 복사 및 이동 생성 및 할당 작업을 수행할 비트 패턴을 자동으로 멤버 단위 복사 또는 비정적 데이터 멤버의 이동 합니다. 이동 또는 복사 작업 없거나 소멸자가 선언 된 경우에 작업 생성은 이동 합니다. 기본 복사 생성자가 복사 생성자가 선언 된 경우에 생성 됩니다. 이동 작업을 선언 하는 경우 암시적으로 삭제 됩니다. 기본 복사 할당 연산자 복사 할당 연산자를 명시적으로 선언 하는 경우에 생성 됩니다. 이동 작업을 선언 하는 경우 암시적으로 삭제 됩니다.

## <a name="see-also"></a>참고자료

[C++ 언어 참조](cpp-language-reference.md)
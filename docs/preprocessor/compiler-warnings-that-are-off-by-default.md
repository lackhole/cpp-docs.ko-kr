---
title: 기본적으로 해제되어 있는 컴파일러 경고
ms.date: 05/30/2018
helpviewer_keywords:
- warnings, compiler
- cl.exe compiler, setting options
ms.assetid: 69809cfb-a38a-4035-b154-283a61938df8
ms.openlocfilehash: ee2b6097a62a8f1030dc631354f96ec7a33d2f11
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59039399"
---
# <a name="compiler-warnings-that-are-off-by-default"></a>기본적으로 해제 되어 있는 컴파일러 경고

컴파일러는 대부분의 개발자 액세스 하지 유용 하지 때문에 기본적으로 해제 되어 있는 경고를 지원 합니다. 경우에 따라 이전 코드에서 일반적인 관용구 또는 선택 하는 스타일에 대 한 경고는 합니다. 언어에 대 한 Microsoft 확장 사용에 대 한 다른 경고는입니다. 다른 경우에 영역 프로그래머에 게 예기치 않은 또는 정의 되지 않은 동작이 발생할 수 있는 잘못 된 가정을 자주 확인 되는 위치를 나타냅니다. 사용 하도록 설정 하는 경우 라이브러리 헤더에 여러 번 나타날 수 있습니다 이러한 경고 중. C 런타임 라이브러리 및 C++ 표준 라이브러리 내보내기 경고 수준에만 경고가 하고자 [/w4](../build/reference/compiler-option-warning-level.md)합니다.

## <a name="enable-warnings-that-are-off-by-default"></a>기본적으로 해제 되어 있는 경고를 사용 하도록 설정

일반적으로 기본적으로 해제 되어 다음 옵션 중 하나를 사용 하 여 경고를 설정할 수 있습니다.

- **#pragma warning(default :** *warning_number* **)**

   지정된 된 경고 (*warning_number*) 기본 수준에서 사용 가능 합니다. 경고 설명서에 경고의 기본 수준이 포함되어 있습니다.

- **#pragma warning(** *warning_level* **:** *warning_number* **)**

   지정된 된 경고 (*warning_number*) 지정된 된 수준에서 사용 가능 (*warning_level*).

- [/Wall](../build/reference/compiler-option-warning-level.md)

   `/Wall`은 기본적으로 해제되어 있는 모든 경고가 사용되게 만듭니다. 사용 하 여 개별 경고 해제할 수 있습니다이 옵션을 사용 하는 경우는 [/wd](../build/reference/compiler-option-warning-level.md) 옵션입니다.

- [/w*Lnnnn*](../build/reference/compiler-option-warning-level.md)

   이 옵션을 사용 하면 경고 *nnnn* 수준 *L*합니다.

## <a name="warnings-that-are-off-by-default"></a>기본적으로 해제 되어 있는 경고

다음 경고는 Visual Studio 2015 이상 버전에서 기본적으로 해제 되어 됩니다.

|||
|-|-|
|[C4061](../error-messages/compiler-warnings/compiler-warning-level-4-c4061.md) (수준 4)|열거자 '*식별자*열거형의 스위치' 에서'*열거형*' case 레이블에 의해 명시적으로 처리 하지 않습니다|
|[C4062](../error-messages/compiler-warnings/compiler-warning-level-4-c4062.md) (수준 4)|열거자 '*식별자*열거형의 스위치' 에서'*열거형*' 처리 되지 않습니다|
| [C4165](../error-messages/compiler-warnings/compiler-warning-level-1-c4165.md) (수준 1) | 'Bool'; 'HRESULT' 변환 되는 원하는 작업 인지 입니까? |
| [C4191](../error-messages/compiler-warnings/compiler-warning-level-3-c4191.md) (수준 3)|'*연산자*': 안전 하지 않은 변환 '*type_of_expression*'to'*type_required*'|
|[C4242](../error-messages/compiler-warnings/compiler-warning-level-4-c4242.md) (수준 4)|'*식별자*': 변환할 '*type1*'to'*type2*', 데이터 손실 될 수 있습니다|
|[C4254](../error-messages/compiler-warnings/compiler-warning-level-4-c4254.md) (수준 4)|'*연산자*': 변환할 '*type1*'to'*type2*', 데이터 손실 될 수 있습니다|
|[C4255](../error-messages/compiler-warnings/compiler-warning-level-4-c4255.md) (수준 4)|'*함수*': 함수 프로토타입을 입력 하지 않았습니다. '()'에서 '(void)'로 변환|
|[C4263](../error-messages/compiler-warnings/compiler-warning-level-4-c4263.md) (수준 4)|'*함수*': 멤버 함수가 기본 클래스 가상 멤버 함수를 재정의 하지 않습니다|
|[C4264](../error-messages/compiler-warnings/compiler-warning-level-1-c4264.md) (수준 1)|'*virtual_function*': 재정의 기본 가상 멤버 함수에 대해 사용할 수 없습니다 '*클래스*'; 함수가 숨겨집니다.|
|[C4265](../error-messages/compiler-warnings/compiler-warning-level-3-c4265.md) (수준 3)|'*클래스*': 클래스에 가상 함수가 있지만 소멸자는 가상이 아닙니다|
|[C4266](../error-messages/compiler-warnings/compiler-warning-level-4-c4266.md) (수준 4)|'*함수*': 재정의 기본 가상 멤버 함수에 대해 사용할 수 없습니다 '*형식*'; 함수가 숨겨집니다.|
|[C4287](../error-messages/compiler-warnings/compiler-warning-level-3-c4287.md) (수준 3)|'*연산자*': 서명 되지 않은 또는 음의 상수가 일치 하지 않습니다|
|[C4289](../error-messages/compiler-warnings/compiler-warning-level-4-c4289.md) (수준 4)|비표준 확장이 사용 됨: '*var*': for 루프에서 선언 된 루프 제어 변수가 for 루프 범위 외부에서 사용 됩니다|
|[C4296](../error-messages/compiler-warnings/compiler-warning-level-4-c4296.md) (수준 4)|'*연산자*': 식이 항상 false입니다.|
|[C4339](../error-messages/compiler-warnings/compiler-warning-level-4-c4339.md) (수준 4)|'*형식*':이 형식 사용 하면 런타임 예외가 발생할 수 있습니다 CLR 메타 데이터에 정의 되지 않은 형식이 사용 되었습니다|
|[C4342](../error-messages/compiler-warnings/compiler-warning-level-1-c4342.md) (수준 1)|동작 변경: '*함수*' 호출 되었지만 이전 버전에서는 멤버 연산자가 호출|
|[C4350](../error-messages/compiler-warnings/compiler-warning-level-1-c4350.md) (수준 1)|동작 변경: '*member1*'대신 호출'*member2*'|
|[C4355](../error-messages/compiler-warnings/compiler-warning-c4355.md)|'this' : 기본 멤버 이니셜라이저 목록에서 사용되었습니다.|
|[C4365](../error-messages/compiler-warnings/compiler-warning-level-4-c4365.md) (수준 4)|'*동작*': 변환할 '*type_1*'to'*type_2*', signed 또는 unsigned 일치 하지 않습니다.|
|C4370 (수준 3)|압축 기능이 향상되어 이전 버전의 컴파일러에서 클래스 레이아웃이 변경되었습니다.|
|[C4371](../error-messages/compiler-warnings/c4371.md) (수준 3)|'*classname*': 멤버를 잘 압축 했기 때문에 컴파일러의 이전 버전에서 클래스 레이아웃이 변경 될 수 있습니다 '*멤버*'|
|C4388 (수준 4)|signed 또는 unsigned가 일치하지 않습니다.|
|[C4412](../error-messages/compiler-warnings/compiler-warning-level-2-c4412.md) (수준 2)|'*함수*': 함수 시그니처에 형식 '*형식*'; C++ 개체는 순수 코드 간에 전달 하는 안전 하지 않은 혼합형 / 네이티브|
|C4426 (수준 1)|헤더를 포함 한 후 변경 된 최적화 플래그 #pragma optimize () 때문일 수 있습니다 <sup>14.1</sup>|
|[C4435](../error-messages/compiler-warnings/compiler-warning-level-4-c4435.md) (수준 4)|'*class1*' : 가상 기본으로 인해/vd2의 개체 레이아웃이 변경 됩니다 '*class2*'|
|[C4437](../error-messages/compiler-warnings/compiler-warning-level-4-c4437.md) (수준 4)|가상 기본 사이의 dynamic_cast가 '*class1*'to'*class2*' 일부 컨텍스트에서 실패할 수 있습니다|
|C4444 (수준 3)|이 컨텍스트에서는 최상위 '__unaligned'가 구현되지 않았습니다.|
|[C4464](../error-messages/compiler-warnings/c4464.md) (수준 4)|include에 상대 경로 '..'|
|[C4471](../error-messages/compiler-warnings/compiler-warning-level-4-c4471.md) (수준 4)|범위가 지정 되지 않은 열거형의 정방향 선언에는 기본 형식 (int로 가정) 있어야 합니다. <sup>권한</sup>|
|C4472 (수준 1)|'*식별자*'가 네이티브 열거형: 관리 되는 열거형을 선언 하려면 액세스 지정자 (전용/공용)를 추가 합니다.|
|[C4514](../error-messages/compiler-warnings/compiler-warning-level-4-c4514.md) (수준 4)|'*함수*': 참조 되지 않은 인라인 함수를 제거 했습니다|
|[C4536](../error-messages/compiler-warnings/compiler-warning-level-4-c4536.md) (수준 4)|'type name': 형식-이름이 메타 데이터 한계인 초과 '*제한*' 문자|
|[C4545](../error-messages/compiler-warnings/compiler-warning-level-1-c4545.md) (수준 1)|쉼표 앞의 식이 인수 목록이 없는 함수로 계산됩니다.|
|[C4546](../error-messages/compiler-warnings/compiler-warning-level-1-c4546.md) (수준 1)|쉼표 앞의 함수에 인수 목록이 없습니다.|
|[C4547](../error-messages/compiler-warnings/compiler-warning-level-1-c4547.md) (수준 1)|'*연산자*': 쉼표 효과가 없습니다; 앞의 연산자 파생 작업이 있는 연산자 여야 합니다.|
|[C4548](../error-messages/compiler-warnings/compiler-warning-level-1-c4548.md) (수준 1)|쉼표 앞의 식은 의미 없는 식입니다. 파생 작업이 있는 식이어야 합니다.|
|[C4549](../error-messages/compiler-warnings/compiler-warning-level-1-c4549.md) (수준 1)|'*operator1*': 쉼표 앞의 연산자는 의미 없는 사용 하려고 했습니까 '*operator2*'?|
|[C4555](../error-messages/compiler-warnings/compiler-warning-level-1-c4555.md) (수준 1)|식이 효과가 없습니다. 파생 작업이 있는 식이어야 합니다.|
|[C4557](../error-messages/compiler-warnings/compiler-warning-level-3-c4557.md) (수준 3)|'__assume' 효과가 있습니다. '*효과*'|
|[C4571](../error-messages/compiler-warnings/compiler-warning-level-4-c4571.md) (수준 4)|정보: 시각적 개체의 catch (...) 의미 체계가 변경 C++ 7.1; 구조적된 예외 (SEH) 변경 되었습니다.|
|C4574 (수준 4)|'*식별자*'0 '으로 정의 된': 사용 하려고 했습니까 ' #if *식별자*'?|
|C4577 (수준 1)|' noexcept' 처리 모드를 지정 합니다; 예외가 사용 예외 시 종료가 보장 되지 않습니다. /EHsc를 지정 합니다.|
|C4582 (수준 4)|'*형식*': 생성자가 암시적으로 호출 되지 않습니다|
|C4583 (수준 4)|'*형식*': 소멸자가 암시적으로 호출 되지 않습니다|
|C4587 (수준 1)|'*anonymous_structure*': 동작 변경: 생성자가 더 이상 암시적으로 호출|
|C4588 (수준 1)|'*anonymous_structure*': 동작 변경: 소멸자가 더 이상 암시적으로 호출 되 고 없습니다.|
|C4596 (수준 4)|'*식별자*': 멤버 선언의 정규화 된 이름이 잘못 되었습니다 <sup>14.3</sup> <sup>권한</sup>|
|C4598 (수준 1 및 수준 3)|' #include "*머리글*"': 헤더 번호 *번호* 미리 컴파일된 헤더에서 해당 위치의 현재 컴파일의 일치 하지 않습니다 <sup>14.3</sup>|
|C4599 (수준 3)|'*옵션* *경로*': 명령줄 인수 번호 *번호* 미리 컴파일된 헤더와 일치 하지 않습니다 <sup>14.3</sup>|
|C4605 (수준 1)|' /D*매크로*' 현재 명령줄에서 지정 되었지만 미리 컴파일된 헤더 빌드 했을 때 지정 되지 않았습니다|
|[C4608](../error-messages/compiler-warnings/compiler-warning-level-3-c4608.md) (수준 3)|'*union_member*'에 이미 초기화 이니셜라이저 목록의 다른 공용 구조체 멤버'*union_member*' <sup>권한</sup>|
|[C4619](../error-messages/compiler-warnings/compiler-warning-level-3-c4619.md) (수준 3)|#pragma 경고: 방법이 없는 경고 번호 '*번호*'|
|[C4623](../error-messages/compiler-warnings/compiler-warning-level-4-c4623.md) (수준 4)|'derived class': 기본 클래스의 기본 생성자에 액세스할 수 없으므로 기본 생성자를 생성할 수 없습니다.|
|[C4625](../error-messages/compiler-warnings/compiler-warning-level-4-c4625.md) (수준 4)|'derived class': 기본 클래스의 복사 생성자에 액세스할 수 없으므로 복사 생성자를 생성할 수 없습니다.|
|[C4626](../error-messages/compiler-warnings/compiler-warning-level-4-c4626.md) (수준 4)|'derived class': 기본 클래스의 대입 연산자에 액세스할 수 없으므로 대입 연산자를 생성할 수 없습니다.|
|[C4628](../error-messages/compiler-warnings/compiler-warning-level-1-c4628.md) (수준 1)|-Ze에는 digraph가 지원되지 않습니다. 문자 시퀀스 '*digraph*'에 대 한 대체 토큰으로 해석 되지 않는'*char*'|
|[C4640](../error-messages/compiler-warnings/compiler-warning-level-3-c4640.md) (수준 3)|'*인스턴스*': 지역 정적 개체를 생성할 때 스레드로부터 안전한 아닙니다.|
| C4643 (수준 4) | 정방향 선언 '*식별자*' 표준에서 허용 하지 않는 네임 스페이스에는 C++ 표준입니다. <sup>15.8</sup> |
|C4647 (수준 3)|동작 변경: __is_pod (*형식*) 이전 버전에 다른 값|
|C4654 (수준 4)|앞에 배치 하는 코드에는 미리 컴파일된 헤더 포함 줄은 무시 됩니다. 미리 컴파일된 헤더에 코드를 추가 합니다. <sup>14.1</sup>|
|[C4668](../error-messages/compiler-warnings/compiler-warning-level-4-c4668.md) (수준 4)|'*기호*'에 대해 '0'으로 바꾸기 전처리기 매크로로 정의 되지 않은'*지시문*'|
|[C4682](../error-messages/compiler-warnings/compiler-warning-level-4-c4682.md) (수준 4)|'*기호*': 방향 매개 변수 특성을 지정 하지, 기본적으로 [in]|
|[C4686](../error-messages/compiler-warnings/compiler-warning-level-3-c4686.md) (수준 3)|'*사용자 정의 형식*': 동작 변경 되었을 수 있습니다, udt 반환 호출 규칙이|
|[C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) (수준 1)|'*함수*': 전용이 아닌 멤버의 시그니처에 어셈블리 전용 네이티브 형식 '*native_type*'|
|[C4710](../error-messages/compiler-warnings/compiler-warning-level-4-c4710.md) (수준 4)|'*함수*': 함수를 인라이닝 하지 못했습니다|
|[C4738](../error-messages/compiler-warnings/compiler-warning-level-3-c4738.md) (수준 3)|32비트 float 결과를 메모리에 저장하면 성능이 저하될 수 있습니다.|
|[C4746](../error-messages/compiler-warnings/compiler-warning-c4746.md)|volatile 액세스 '*식을*' 하려면 /volatile:\<iso&#124;ms > __iso_volatile_load/store 내장 함수를 사용해 설정 합니다.|
|C4749 (수준 4)|조건부로 지원 됨: offsetof가 비표준 레이아웃이 아닌 형식 '*형식*'|
|C4767 (수준 4)|섹션 이름 '*기호*' 8 자 보다 긴 및 링커에서 잘립니다|
|C4768 (수준 3)|링크 사양 앞의 __declspec 특성은 무시 됩니다.|
|C4774 (수준 4)|'*문자열*': 서식 문자열 인수에 예상 *번호* 이 문자열 리터럴|
|C4777 (수준 4)|'*함수*': 서식 문자열 '*문자열*'형식의 인수가 필요 합니다.'*type1*', 하지만 variadic 인수 *번호* 형식이 '*type2*'|
|C4786 (수준 3)|'*기호*': 개체 이름이 잘렸습니다 '*번호*' 디버그 정보에는 문자|
| [C4800](../error-messages/compiler-warnings/compiler-warning-level-3-c4800.md) (수준 4) | 암시적 변환에서 '*형식*' bool로 합니다. 가능한 정보 손실 <sup>16.0</sup> |
|[C4820](../error-messages/compiler-warnings/compiler-warning-level-4-c4820.md) (수준 4)|'*바이트*'바이트 채움 문자가 추가 됨' 구문 뒤*member_name*'|
| [C4822](../error-messages/compiler-warnings/compiler-warning-level-1-c4822.md) (수준 1) | '*멤버*': 지역 클래스 멤버 함수에 본문이 없습니다. |
|C4826 (수준 2)|변환에서 '*type1*'to'*type2*' 부호가 확장 됩니다. 이 예기치 않은 런타임 동작이 발생할 수 있습니다.|
|C4837 (수준 4)|삼중 자가 발견 되었습니다. '?? *문자*'로 대체'*문자*'|
|C4841 (수준 4)|비표준 확장이 사용 됨: 복합 멤버 지정 자가 offsetof에에서 사용|
|C4842 (수준 4)|다중 상속을 사용 하는 형식에 적용 된 'offsetof' 결과 컴파일러 릴리스 간에 일관 되도록 보장 되지 않습니다.|
|[C4868](../error-messages/compiler-warnings/compiler-warning-c4868.md) (수준 4)|'_파일_(*line_number*)' 컴파일러는 중괄호로 묶인된 초기화 목록에서 왼쪽에서 오른쪽 계산 순서를 적용할 수 없습니다.|
|[C4905](../error-messages/compiler-warnings/compiler-warning-level-1-c4905.md) (수준 1)|와이드 문자열 리터럴을 'LPSTR'로 캐스팅했습니다.|
|[C4906](../error-messages/compiler-warnings/compiler-warning-level-1-c4906.md) (수준 1)|문자열 리터럴을 'LPWSTR'로 캐스팅했습니다.|
|[C4917](../error-messages/compiler-warnings/compiler-warning-level-1-c4917.md) (수준 1)|'*declarator*': GUID 클래스, 인터페이스 또는 네임 스페이스를 사용 하 여 연결할 수만|
|[C4928](../error-messages/compiler-warnings/compiler-warning-level-1-c4928.md) (수준 1)|복사 초기화가 잘못되었습니다. 사용자 정의 변환이 암시적으로 두 번 이상 적용되었습니다.|
|[C4931](../error-messages/compiler-warnings/compiler-warning-level-4-c4931.md) (수준 4)|number비트 포인터에 대한 형식 라이브러리를 빌드했다고 간주합니다.|
|[C4946](../error-messages/compiler-warnings/compiler-warning-level-1-c4946.md) (수준 1)|reinterpret_cast가 관련된 클래스 간의 사용 되었습니다. '*class1*'및'*class2*'|
|C4962|'*함수*': 최적화 프로필 데이터가 일관성이 없는 상태가 발생 하므로 사용 하지 않도록 설정 하는 프로필 기반 최적화|
|[C4986](../error-messages/compiler-warnings/compiler-warning-c4986.md) (수준 4)|'*기호*': 예외 사양이 이전 선언과 일치 하지 않습니다|
|C4987 (수준 4)|비표준 확장 사용: 'throw (...)'|
|C4988 (수준 4)|'*기호*': 변수가 클래스/함수 범위 외부 선언|
|C5022|'*형식*': 이동 생성자가 여러 개 지정|
|C5023|'*형식*': 지정 된 여러 명의 이동 할당 연산자|
|C5024 (수준 4)|'*형식*': 이동 생성자가 암시적으로 삭제 된 것으로 정의 됩니다|
|C5025 (수준 4)|'*형식*': 이동 대입 연산자가 삭제 된 것으로 암시적으로 정의 됩니다|
|C5026 (수준 1 및 수준 4)|'*형식*': 이동 생성자가 암시적으로 삭제 된 것으로 정의 됩니다|
|C5027 (수준 1 및 수준 4)|'*형식*': 이동 대입 연산자가 삭제 된 것으로 암시적으로 정의 됩니다|
|C5029 (수준 4)|비표준 확장이 사용 됨: 맞춤 특성 C++ 변수, 데이터 멤버 및 태그 형식에만 적용|
|C5031이 발생 (수준 4)|#pragma warning (pop): 다른 파일에서 푸시된 경고 상태 팝업 불일치 가능성 <sup>14.1</sup>|
|C5032 (수준 4)|해당 없음 #pragma warning (pop이) 사용 하 여 #pragma warning (push) 검색 <sup>14.1</sup>|
|C5034|내장 함수의 사용 하 여 '*내장*' 함수 *함수* 게스트 코드로 컴파일됩니다 <sup>15.3</sup>|
|C5035|기능을 사용 하 여 '*기능*' 함수 *함수* 게스트 코드로 컴파일됩니다 <sup>15.3</sup>|
|C5036 (수준 1)|/ hybrid:x86arm64를 사용 하 여 컴파일할 때의 varargs 함수 포인터 변환이 있습니다. '*type1*'to'*type2*' <sup>15.3</sup>|
|[C5038](../error-messages/compiler-warnings/c5038.md) (수준 4)|데이터 멤버 '*member1*'다음에 초기화 됩니다 데이터 멤버'*member2*' <sup>15.3</sup>|
|C5039 (수준 4)|'*함수*':-ehc extern C 함수에 대 한 포인터 또는 참조 잠재적인 throw 함수에 전달 합니다. 이 함수가 예외를 throw 하는 경우 정의 되지 않은 동작이 발생할 수 있습니다. <sup>15.5</sup>|
|C5042 (수준 3)|'*함수*': 블록 범위의 함수 선언은 표준에 지정 된 'inline' 일 수 없습니다 C++; 'inline' 지정자를 제거 <sup>15.5</sup>|
|[C5045](../error-messages/compiler-warnings/c5045.md)|컴파일러는 /Qspectre 스위치가 지정 하는 경우 메모리 로드를 위해 스펙터 완화를 삽입 <sup>15.7</sup>|

<sup>14.1</sup> 이 경고는 Visual Studio 2015 업데이트 1부터 사용할 수 있습니다.<br/>
<sup>14.3</sup> 이 경고는 Visual Studio 2015 업데이트 3부터 사용할 수 있습니다.<br/>
<sup>15.3</sup> 이 경고는 Visual Studio 2017 버전 15.3부터 사용할 수 있습니다.<br/>
<sup>15.5</sup> 이 경고는 Visual Studio 2017 버전 15.5부터 사용할 수 있습니다.<br/>
<sup>15.7</sup> 이 경고는 Visual Studio 2017 버전 15.7부터 사용할 수 있습니다.<br/>
<sup>15.8</sup> 이 경고는 Visual Studio 2017 버전 15.8부터 사용할 수 있습니다.<br/>
::: moniker range=">= vs-2019"
<sup>16.0</sup> 이 경고는 Visual Studio 2019 RTM부터 사용할 수 있습니다.<br/>
::: moniker-end
<sup>권한</sup> 하지 않는 한이 경고는 해제 되어 합니다 [관대 한 /-](../build/reference/permissive-standards-conformance.md) 컴파일러 옵션을 설정 합니다.<br/>

## <a name="warnings-off-by-default-in-earlier-versions"></a>이전 버전에서 기본적으로 해제 경고

이러한 경고는 버전의 Visual Studio 2015 이전 컴파일러에서 기본적으로 해제 했습니다.

|||
|-|-|
|[C4302](../error-messages/compiler-warnings/compiler-warning-level-2-c4302.md) (수준 2)|'*변환이*':에서 잘림 '*type1*'to'*type2*'|
|[C4311](../error-messages/compiler-warnings/compiler-warning-level-1-c4311.md) (수준 1)|'*변수에*':에서 포인터 잘림 '*유형*'to'*형식*'|
|[C4312](../error-messages/compiler-warnings/compiler-warning-level-1-c4312.md) (수준 1)|'*작업이*': 변환할 '*type1*'to'*type2*' 큰 크기의|
|[C4319](../error-messages/compiler-warnings/compiler-warning-level-1-c4319.md) (수준 1)|'*연산자*': 0 확장 '*type1*'to'*type2*' 큰 크기의|

이 경고는 버전의 Visual Studio 2012 이전 컴파일러에서 기본적으로 꺼져 있었습니다.

|||
|-|-|
|[C4431](../error-messages/compiler-warnings/compiler-warning-level-4-c4431.md) (수준 4)|형식 지정자가 없습니다. int로 가정합니다. 참고: C 기본 int를 더 이상 지원|

## <a name="see-also"></a>참고자료

[warning](../preprocessor/warning.md)
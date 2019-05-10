---
title: 컴파일러 경고(수준 1) C4503
ms.date: 05/14/2018
f1_keywords:
- C4503
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
ms.openlocfilehash: 94c88511d87c3adf3cf5687a94948c83ebc5b3d5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160980"
---
# <a name="compiler-warning-level-1-c4503"></a>컴파일러 경고(수준 1) C4503

> '*식별자*': 데코레이팅된 이름 길이 초과 했으므로 이름이 잘립니다

## <a name="remarks"></a>설명

이 컴파일러 경고가 사용 되지 않는 및 Visual Studio 2017 및 이후 컴파일러에서 생성 되지 않습니다.

트 데코 레이 된 이름 (4096) 컴파일러 한계를 초과 하 고 잘렸습니다. 이 경고와 잘림을 방지 하려면 인수 개수 또는 사용 되는 식별자 이름 길이 줄입니다. 데코레이팅된 이름 하는 컴파일러 한계 보다 더 이상 적용 하는 해시 이름 충돌의 위험에 있지 않습니다.

이전 버전의 Visual Studio를 사용 하는 경우에 코드 템플릿을 포함 하는 경우이 경고를 발생 수 반복적으로 서식 파일에서 특수화 된 합니다. 예를 들어 맵의 지도 (에서 C++ 표준 라이브러리)입니다. 이 이런 경우 변경할 수 있습니다 프로그램 typedef 형식 (을 **구조체**예를 들어) 맵을 포함 하는 합니다.

그러나 코드를 재구성 하지 결정할 수 있습니다.  C4503를 생성 하는 응용 프로그램에 전달할 수 있지만의 잘린된 기호 링크 시간 오류를 받게 되 면 오류에 있는 기호의 형식을 확인 하는 것이 어려울 수 있습니다. 월도 디버깅 어려울 것입니다. 디버거는 데 어려움이 있으므로 이러한 기호 이름을 형식 이름으로 매핑 있을 수 있습니다. 그러나 프로그램의 정확성 영향을 받지 않습니다 잘린된 이름입니다.

## <a name="example"></a>예제

다음 샘플에서는 Visual Studio 2017 이전 컴파일러에서 C4503를 생성합니다.

```cpp
// C4503.cpp
// compile with: /W1 /EHsc /c
// C4503 expected
#include <string>
#include <map>

class Field{};

typedef std::map<std::string, Field> Screen;
typedef std::map<std::string, Screen> WebApp;
typedef std::map<std::string, WebApp> WebAppTest;
typedef std::map<std::string, WebAppTest> Hello;
Hello MyWAT;
```

이 샘플에 C4503를 해결 하려면 코드를 다시 작성 하는 방법을 보여 줍니다.

```cpp
// C4503b.cpp
// compile with: /W1 /EHsc /c
#include <string>
#include <map>

class Field{};

struct Screen2 {
   std::map<std::string, Field> Element;
};

struct WebApp2 {
   std::map<std::string, Screen2> Element;
};

struct WebAppTest2 {
   std::map<std::string, WebApp2> Element;
};

struct Hello2 {
   std::map<std::string, WebAppTest2> Element;
};

Hello2 MyWAT2;
```
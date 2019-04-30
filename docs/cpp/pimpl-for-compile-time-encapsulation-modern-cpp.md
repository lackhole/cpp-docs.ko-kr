---
title: 컴파일 시간 캡슐화에 대한 Pimpl(모던 C++)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
ms.openlocfilehash: 6e114e2802dd4b2e5d1497867e2224be90c4752d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396108"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>컴파일 시간 캡슐화에 대한 Pimpl(모던 C++)

캡슐화 pimpl 관용구* 숨기기는 결합을 최소화하고 분리 인터페이스를 구현하는 최신 C++ 기술입니다. 캡슐화 Pimpl는 짧은 "포인터"를 구현합니다. 개념에 익숙할 수 있지만 명칭 또는 컴파일러 방화벽 관용구와 같은 다른 이름으로 이미 알려져 있습니다.

## <a name="why-use-pimpl"></a>캡슐화 pimpl를 사용 하는 이유는?

캡슐화 pimpl 관용구 소프트웨어 개발 수명 주기를 개선 하는 방법을 다음과 같습니다.

- 컴파일 종속성 최소화 합니다.

- 인터페이스와 구현을 분리 합니다.

- 이식성입니다.

## <a name="pimpl-header"></a>캡슐화 Pimpl 헤더

```cpp
// my_class.h
class my_class {
   //  ... all public and protected stuff goes here ...
private:
   class impl; unique_ptr<impl> pimpl; // opaque type here
};
```

캡슐화 pimpl 관용구 rebuild 단계적 및 불안정 개체 레이아웃을 피할 수 있습니다. (전이적) 인기 있는 형식에 대 한 적합 합니다.

## <a name="pimpl-implementation"></a>캡슐화 Pimpl 구현

정의 된 `impl` .cpp 파일에서 클래스입니다.

```cpp
// my_class.cpp
class my_class::impl {  // defined privately here
  // ... all private data and functions: all of these
  //     can now change without recompiling callers ...
};
my_class::my_class(): pimpl( new impl )
{
  // ... set impl values ...
}
```

## <a name="best-practices"></a>최선의 방법

Throw 되지 않는 스왑 특수화에 대 한 지원을 추가할지 여부를 고려 합니다.

## <a name="see-also"></a>참고자료

[C++의 진화(모던 C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)

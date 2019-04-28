---
title: 리소스를 소유하는 오브젝트(RAII)
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
ms.openlocfilehash: 5705fc1996343141b13e37d1267b2e8c981c1eba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245091"
---
# <a name="objects-own-resources-raii"></a>리소스를 소유하는 오브젝트(RAII)

소유된 리소스 개체인 것을 확인합니다. 이 원칙은 "리소스 획득 초기화" 또는 "RAII" 라고 알려져 있습니다.

## <a name="example"></a>예제

이름 있는 개별 개체의 생성자 인수로 "new" 개체를 전달합니다(대부분 unique_ptr).

```cpp
void f() {
    unique_ptr<widget> p( new widget() );
    my_class x( new widget() );
    // ...
} // automatic destruction and deallocation for both widget objects
  // automatic exception safety, as if "finally { p->dispose(); x.w.dispose(); }"
```

이를 소유하는 다른 개체에 항상 즉시 새로운 리소스를 전달합니다.

```cpp
void g() {
    other_class y( OpenFile() );
    // ...
} // automatic closing and release for file resource
  // automatic exception safety, as if "finally { y.file.dispose(); }"
```

## <a name="see-also"></a>참고자료

[C++의 진화(모던 C++)](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 언어 참조](../cpp/cpp-language-reference.md)<br/>
[C++ 표준 라이브러리](../standard-library/cpp-standard-library-reference.md)

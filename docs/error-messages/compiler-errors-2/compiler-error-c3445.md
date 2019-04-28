---
title: 컴파일러 오류 C3445
ms.date: 04/10/2017
f1_keywords:
- C3445
helpviewer_keywords:
- C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
ms.openlocfilehash: 2eddeb5a56c953ca0864e29187fbe28c53bdee24
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62328655"
---
# <a name="compiler-error-c3445"></a>컴파일러 오류 C3445

> 복사-목록 초기화의 '*형식*' 명시적 생성자를 사용할 수 없습니다.

ISO c++17 표준에 따라 컴파일러는 초기화-복사-목록에서에서 오버 로드 확인에 대 한 명시적 생성자를 고려해 야 하는 데 필요한 하지만 오버 로드 하는 실제로 선택 되는 경우 오류가 발생 해야 합니다.

Visual Studio 2017부터 컴파일러는 이니셜라이저 목록을 사용 하 여 개체 만들기와 관련 된 Visual Studio 2015에서 발견 되지 않은 오류를 찾습니다. 이러한 오류 충돌 또는 런타임 시 정의 되지 않은 동작이 발생할 수 있습니다.

## <a name="example"></a>예제

다음 샘플 C3445를 생성합니다.

```cpp
// C3445.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 };     // error C3445: copy-list-initialization of
                      //     'A' cannot use an explicit constructor
}
```

오류를 수정 하려면 직접 초기화를 대신 사용 합니다.

```cpp
// C3445b.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1{ 1 };
}
```

---
title: 컴파일러 경고(수준 1) C4743
ms.date: 11/04/2016
f1_keywords:
- C4743
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
ms.openlocfilehash: d17fd65f1108aab6e3ce97ec75c0ffb899c06cda
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152010"
---
# <a name="compiler-warning-level-1-c4743"></a>컴파일러 경고(수준 1) C4743

'*형식*'다른 크기의 '*file1*'및'*file2*': *번호* 하 고 *번호* 바이트

컴파일러에서 확인 하 고 두 파일에서 참조 하거나 정의한 외부 변수가 해당 파일에 대 한 다양 한 종류의 변수 크기 *file1* 변수의 크기에서 다른 *file2*.

있는 경우 중요 한 경우에 대 한이 경고를 내보낼 수 있습니다 C++입니다. 선언과 동일 하지 않은 경우 및 해당 선언에는 가상 함수를 포함 하는 경우 서로 다른 두 파일에 동일한 이름의 동일한 형식을 선언 하는 경우 컴파일러는 가상 함수 테이블에 대 한 경고 C4744를 내보낼 수 있습니다. 경고에는 두 개의 서로 다른 크기의 가상 함수 테이블에는 동일한 형식에 대 한 링커 실행 파일을 통합할 수 중 하나를 선택 해야 하기 때문에 발생 합니다.  잘못 된 가상 함수를 호출 하는 프로그램에서 발생할 수 있습니다이 가능 합니다.

이 경고를 해결 하려면 같은 형식 정의 사용 하거나 변수 또는 형식에 대해 다른 이름을 사용 합니다.

## <a name="example"></a>예제

이 샘플에는 형식의 한 정의가 포함 됩니다.

```
// C4743a.cpp
// compile with: /c
class C {
public:
    virtual void f1(void);
    virtual void f2(void);
    virtual void f3(void);
};

void C::f1(void) {}
void C::f2(void) {}
void C::f3(void) {}
C q;
```

## <a name="example"></a>예제

다음 샘플 C4743를 생성합니다.

```
// C4743b.cpp
// compile with: C4743a.cpp /W1 /GL /O2
// C4743 expected
class C {
public:
    virtual void f1(void);
    virtual void f2(void);
    virtual void f3(void);
    virtual void f4(void);
    virtual void f5(void);
};

void C::f4(void) {}
void C::f5(void) {}
C x;

int main() {}
```
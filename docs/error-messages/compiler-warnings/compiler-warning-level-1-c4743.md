---
title: 컴파일러 경고(수준 1) C4743
ms.date: 05/13/2019
f1_keywords:
- C4743
helpviewer_keywords:
- C4743
ms.assetid: 2ee76ea3-77f3-4c2f-9a57-0751823c89fd
ms.openlocfilehash: 53ead0e34b55eca44399cee09f1947a12e1eadd3
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65611837"
---
# <a name="compiler-warning-level-1-c4743"></a>컴파일러 경고(수준 1) C4743

'*형식*'다른 크기의 '*file1*'및'*file2*': *번호* 하 고 *번호* 바이트

컴파일러에서 확인 하 고 두 파일에서 참조 하거나 정의한 외부 변수가 해당 파일에 대 한 다양 한 종류의 변수 크기 *file1* 변수의 크기에서 다른 *file2*.

## <a name="remarks"></a>설명

있는 경우는 중요 한 경우에 대 한이 경고를 내보낼 수 있습니다 C++입니다. 선언과 동일 하지 않은 경우 및 해당 선언에는 가상 함수를 포함 하는 경우 서로 다른 두 파일에 동일한 이름의 동일한 형식을 선언 하는 경우 컴파일러는 가상 함수 테이블에 대 한 경고 C4744를 내보낼 수 있습니다. 경고에는 두 개의 다른 크기의 가상 함수 테이블에는 동일한 형식에 대 한 링커 실행 파일을 통합할 수 중 하나를 선택 해야 하기 때문에 발생 합니다.  잘못 된 가상 함수를 호출 하는 프로그램에서 발생할 수 있습니다 것 같습니다.

이 경고를 해결 하려면 같은 형식 정의 사용 하거나 변수 또는 형식에 대해 다른 이름을 사용 합니다.

## <a name="example"></a>예제

다음 샘플 C4743를 생성합니다. 이 컴파일하려면 파일을 모두 동일한 폴더에 배치 다음 실행  

```cmd
cl /EHsc /W1 /GL /O2 C4743a.cpp C4743b.cpp
```

```cpp
// C4743a.cpp
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

```cpp
// C4743b.cpp
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

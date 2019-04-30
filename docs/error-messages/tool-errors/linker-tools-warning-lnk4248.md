---
title: 링커 도구 경고 LNK4248
ms.date: 11/04/2016
f1_keywords:
- LNK4248
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
ms.openlocfilehash: db9432c505b7348c9bef5ed34aac1cb4edecb17b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352525"
---
# <a name="linker-tools-warning-lnk4248"></a>링커 도구 경고 LNK4248

확인 되지 않은 형식 정의 토큰 (토큰) 'type'; 이미지를 실행할 수 없습니다.

형식을은 MSIL 메타 데이터의 정의가 없습니다.

MSIL 모듈의 형식에 대 한 정방향 선언만 있으면 LNK4248 발생할 수 있습니다 (사용 하 여 컴파일된 **/clr**), 형식을 MSIL 모듈에서 참조 하는 경우 및 MSIL 모듈에 대 한 정의가 있는 네이티브 모듈을 사용 하 여 연결 된 경우 형식입니다.

이 경우 링커에서 MSIL 메타 데이터에서 네이티브 형식 정의 제공 합니다 하 고 올바른 동작을 제공할 수 있습니다.

그러나 전달 형식 선언을 CLR 형식이 면 다음 링커의 네이티브 형식 정의가 올바르지 않을

자세한 내용은 [/clr(공용 언어 런타임 컴파일)](../../build/reference/clr-common-language-runtime-compilation.md)을 참조하세요.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1. MSIL 모듈의 형식 정의 제공 합니다.

## <a name="example"></a>예제

다음 샘플 LNK4248를 생성합니다. 해결 하는 구조체를 정의 합니다.

```
// LNK4248.cpp
// compile with: /clr /W1
// LNK4248 expected
struct A;
void Test(A*){}

int main() {
   Test(0);
}
```

## <a name="example"></a>예제

다음 샘플에서는 형식의 정의 전달 합니다.

```
// LNK4248_2.cpp
// compile with: /clr /c
class A;   // provide a definition for A here to resolve
A * newA();
int valueA(A * a);

int main() {
   A * a = newA();
   return valueA(a);
}
```

## <a name="example"></a>예제

다음 샘플 LNK4248를 생성합니다.

```
// LNK4248_3.cpp
// compile with: /c
// post-build command: link LNK4248_2.obj LNK4248_3.obj
class A {
public:
   int b;
};

A* newA() {
   return new A;
}

int valueA(A * a) {
   return (int)a;
}
```
---
title: 컴파일러 오류 C3104
ms.date: 11/04/2016
f1_keywords:
- C3104
helpviewer_keywords:
- C3104
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
ms.openlocfilehash: 3b2737bd67798fd467649be175d581ca551e1331
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62404171"
---
# <a name="compiler-error-c3104"></a>컴파일러 오류 C3104

잘못 된 특성 인수입니다.

특성에 잘못 된 인수가 지정 했습니다.

참조 [특성 매개 변수 형식](../../extensions/attribute-parameter-types-cpp-component-extensions.md) 자세한 내용은 합니다.

이 오류는 시각적 개체에 대해 수행한 컴파일러 규칙 작업의 결과로 생성 될 수 없습니다 C++ 2005: 집합체 초기화 목록에서 배열의 형식 추론 됩니다 더 이상 관리 되는 배열, 사용자 지정 특성에 전달 하는 경우. 이제 컴파일러를 사용 하면 이니셜라이저 목록 뿐만 아니라 배열 형식을 지정 해야 합니다.

## <a name="example"></a>예제

다음 샘플 C3104를 생성합니다.

```
// C3104a.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::Class)]
public ref struct ABC : public Attribute {
   ABC(array<int>^){}
   array<double> ^ param;
};

[ABC( {1,2,3}, param = {2.71, 3.14})]   // C3104
// try the following line instead
// [ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]
ref struct AStruct{};
```

## <a name="example"></a>예제

다음 샘플 C3104를 생성합니다.

```
// C3104b.cpp
// compile with: /clr /c
// C3104 expected
using namespace System;

int func() {
   return 0;
}

[attribute(All)]
ref class A {
public:
   A(int) {}
};

// Delete the following 2 lines to resolve.
[A(func())]
ref class B {};

// OK
[A(0)]
ref class B {};
```

---
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: 1d78e8f5116eabf9073205b938156197bf1001a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245247"
---
# <a name="noreturn"></a>noreturn

## <a name="microsoft-specific"></a>Microsoft 전용

이 **`__declspec`** 특성은 함수가 반환되지 않음을 컴파일러에 알립니다. 그 결과 컴파일러는 **__declspec(noreturn)** 함수 호출 후의 코드에 접근할 수 없다는 사실을 인식합니다.

컴파일러가 값을 반환하지 않는 제어 경로를 가진 함수를 발견할 경우 경고(C4715) 또는 오류 메시지(C2202)가 생성됩니다. 반환되지 않는 함수로 인해 제어 경로에 도달할 수 없으면 **__declspec(noreturn)** 를 사용하여 이 경고나 오류가 발생하지 않도록 할 수 있습니다.

> [!NOTE]
>  반환될 함수에 **__declspec(noreturn)** 를 추가하면 정의되지 않은 동작이 발생할 수 있습니다.

## <a name="example"></a>예제

다음 샘플에서는 **else** 절에 return 문이 없습니다.  `fatal`을 **__declspec(noreturn)** 로 선언하면 오류 또는 경고 메시지가 발생하지 않습니다.

```cpp
// noreturn2.cpp
__declspec(noreturn) extern void fatal () {}

int main() {
   if(1)
     return 1;
   else if(0)
     return 0;
   else
     fatal();
}
```

## <a name="see-also"></a>참고 항목

[__declspec](../cpp/declspec.md)<br/>
[키워드](../cpp/keywords-cpp.md)
---
title: 컴파일러 경고(수준 3) C4398
ms.date: 11/04/2016
f1_keywords:
- C4398
helpviewer_keywords:
- C4398
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
ms.openlocfilehash: 4126a1267b41cdf9c0161c7e85a9057b2a301d77
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401971"
---
# <a name="compiler-warning-level-3-c4398"></a>컴파일러 경고(수준 3) C4398

> '*변수*': appdomain이 여러 개 프로세스별 전역 개체가 제대로 작동 하지 않으면 __declspec (appdomain)를 사용 하는 것이 좋습니다.

## <a name="remarks"></a>설명

갖는 가상 함수와 [__clrcall](../../cpp/clrcall.md) 만들어지도록의 네이티브 형식에 호출 규칙을 응용 프로그램 도메인 vtable 당. 여러 응용 프로그램 도메인에서 사용 하는 경우 이러한 변수 올바르게 해결할 수는 없습니다.

명시적으로 변수를 표시 하 여이 경고를 해결할 수 있습니다 `__declspec(appdomain)`합니다. Visual Studio 2017 이전 Visual Studio의 버전을 사용 하 여 컴파일하면이 경고를 해결할 수 있습니다 **/clr: pure**, 기본적으로 appdomain 당 전역 변수를 만드는 합니다. **/clr: pure** 컴파일러 옵션은 Visual Studio 2015에서 사용 되지 않으며 Visual Studio 2017에서 지원 되지 않습니다.

자세한 내용은 [appdomain](../../cpp/appdomain.md) 하 고 [응용 프로그램 도메인 및 시각적 개체 C++ ](../../dotnet/application-domains-and-visual-cpp.md)합니다.

## <a name="example"></a>예제

다음 샘플에서는 C4398 오류가 발생 합니다.

```cpp
// C4398.cpp
// compile with: /clr /W3 /c
struct S {
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall
};

S glob_s;   // C4398
__declspec(appdomain) S glob_s2;   // OK
```
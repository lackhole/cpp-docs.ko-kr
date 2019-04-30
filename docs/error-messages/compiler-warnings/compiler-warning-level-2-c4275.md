---
title: 컴파일러 경고(수준 2) C4275
ms.date: 02/08/2019
f1_keywords:
- C4275
helpviewer_keywords:
- C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
ms.openlocfilehash: 6e0e80d465d77bd4fe99fbcaa98e289b8a4c8b63
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349687"
---
# <a name="compiler-warning-level-2-c4275"></a>컴파일러 경고(수준 2) C4275

> 비-DLL 인터페이스 클래스 *('class_1*'DLL 인터페이스 클래스에 대 한 기준으로 사용'*class_2*'

내보낸된 클래스에는 내보낸 되지 않은 클래스에서 파생 되었습니다.

사용 하 여 클래스를 내보낼 때 데이터 손상의 가능성을 최소화 하려면 [__declspec (dllexport)](../../cpp/dllexport-dllimport.md), 있는지 확인 합니다.

- 모든 정적 데이터는 DLL에서 내보낸 함수를 통해 액세스 됩니다.

- 클래스의 인라인된 메서드가 정적 데이터를 수정할 수 있습니다.

- 클래스의 인라인된 메서드가 없는 CRT 함수 또는 정적 데이터를 사용 하는 다른 라이브러리 함수를 사용 합니다.

- 클래스를 인라인된 함수가 없습니다. 정적 데이터에 액세스 하는 CRT 함수 또는 다른 라이브러리 함수를 사용 합니다.

- 클래스의 메서드가 없는 (에 관계 없이 인라인) 인스턴스화 EXE 및 DLL에 있는 정적 데이터 차이 형식을 사용할 수 있습니다.

가상 함수를 사용 하 여 클래스를 정의 하 고 함수는 DLL 인스턴스화하기 위해 호출할 수를 정의 하 고 형식의 개체를 삭제 하면 클래스를 내보내지 방지할 수 있습니다.  그런 다음 가상 함수 형식에만 호출할 수 있습니다.

시각적 개체에 C4275를 무시할 수 있습니다 C++ 의 형식에서 파생 하는 경우는 C++ 디버그 릴리스에 컴파일 표준 라이브러리 (**/MTd**) 고 컴파일러 오류 메시지 가리킵니다 `_Container_base`.

```cpp
// C4275.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275
```
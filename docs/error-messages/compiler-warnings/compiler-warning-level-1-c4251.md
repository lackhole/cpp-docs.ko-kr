---
title: 컴파일러 경고(수준 1) C4251
ms.date: 11/04/2016
f1_keywords:
- C4251
helpviewer_keywords:
- C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
ms.openlocfilehash: d2fff1d2f30c4ac80af6d5b9ca452fa5f30f5a15
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62207359"
---
# <a name="compiler-warning-level-1-c4251"></a>컴파일러 경고(수준 1) C4251

'identifier': 'type' 클래스를 dll 인터페이스에서 'type2' 클래스의 클라이언트가 사용할 해야 합니다.

사용 하 여 클래스를 내보낼 때 데이터 손상의 가능성을 최소화 하려면 [__declspec (dllexport)](../../cpp/dllexport-dllimport.md), 되어 있는지 확인 합니다.

- 모든 정적 데이터는 DLL에서 내보낸 함수를 통해 액세스 합니다.

- 클래스의 인라인된 메서드가 정적 데이터를 수정할 수 있습니다.

- 클래스의 인라인된 메서드가 없는 CRT 함수를 사용 하거나 정적 데이터를 사용 하 여 다른 라이브러리 함수 (참조 [잠재적 오류 전달 CRT DLL 경계를 넘어 개체](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) 자세한).

- 클래스의 메서드가 없는 (에 관계 없이 인라인) 인스턴스화 EXE 및 DLL에 있는 정적 데이터 차이 형식을 사용할 수 있습니다.

가상 함수를 사용 하 여 클래스를 정의 하 고 함수는 DLL 인스턴스화하기 위해 호출할 수를 정의 하 고 형식의 개체를 삭제 하면 클래스를 내보내지 방지할 수 있습니다.  그런 다음 가상 함수 형식에만 호출할 수 있습니다.

형식에서 파생 하는 경우에 C4251를 무시할 수 있습니다는 C++ 디버그 릴리스에 컴파일 표준 라이브러리 (**/MTd**) 컴파일러 오류 메시지 _Container_base를 참조 하는 위치 및 합니다.

```cpp
// C4251.cpp
// compile with: /EHsc /MTd /W2 /c
#include <vector>
using namespace std;
class Node;
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251
```
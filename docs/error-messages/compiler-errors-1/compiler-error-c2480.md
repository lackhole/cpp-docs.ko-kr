---
title: 컴파일러 오류 C2480
ms.date: 11/04/2016
f1_keywords:
- C2480
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
ms.openlocfilehash: 90016b65d4ddd58da3fb3c5ab6d81322dc0ef394
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62187616"
---
# <a name="compiler-error-c2480"></a>컴파일러 오류 C2480

'identifier': 'thread' 정적 범위의 데이터 항목에만 유효.

사용할 수 없습니다는 `thread` 특성을 자동 변수, 비정적 데이터 멤버, 함수 매개 변수 또는 함수 선언 또는 정의 합니다.

사용 된 `thread` 전역 변수, 정적 데이터 멤버 및 정적 변수에 로컬에 대 한 특성입니다.

다음 샘플에서는 C2480를 생성합니다.

```
// C2480.cpp
// compile with: /c
__declspec( thread ) void func();   // C2480
__declspec( thread ) static int i;   // OK
```
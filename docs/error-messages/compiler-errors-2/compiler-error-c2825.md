---
title: 컴파일러 오류 C2825
ms.date: 11/04/2016
f1_keywords:
- C2825
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
ms.openlocfilehash: 1e2f8e8cd38b90a698994743609892896ef0d1a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406901"
---
# <a name="compiler-error-c2825"></a>컴파일러 오류 C2825

var: 클래스 또는 네임 스페이스 뒤에 하는 경우 여야 ': '

실패 한 시도 정규화 된 이름을 하려고 합니다.

예를 들어 코드에 함수 이름을 시작 하는 함수 선언이 포함 되지 않도록 해야:: 합니다.

## <a name="example"></a>예제

다음 샘플에서는 C2825 오류가 생성 됩니다.

```
// C2825.cpp
typedef int i;
int main() {
   int* p = new int;
   p->i::i();   // C2825
   // try the following line instead
   // p->i::~i();
}
```
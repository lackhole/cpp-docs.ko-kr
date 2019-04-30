---
title: 컴파일러 경고(수준 1) C4742
ms.date: 11/04/2016
f1_keywords:
- C4742
helpviewer_keywords:
- C4742
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
ms.openlocfilehash: 00ac67fec3aafa5a259b5222bd6bb8654210fa61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390427"
---
# <a name="compiler-warning-level-1-c4742"></a>컴파일러 경고(수준 1) C4742

'var'에 'file1' 및 'file2' 다른 맞춤: 수 및 수

참조 또는 두 파일에 정의 된 외부 변수가 해당 파일에 다른 맞춤 이 경고는 컴파일러가 발견 한 경우 내보내집니다 `__alignof` 에 변수 *file1* 에서 다른 `__alignof` 변수와 *file2*합니다. 이 일치 하지 않는 사용 하 여 또는 다른 파일에서 변수를 선언 하는 경우에 호환 되지 않는 형식을 사용 하 여 발생할 수 있습니다 `#pragma pack` 서로 다른 파일에 있습니다.

이 경고를 해결 하려면 같은 형식 정의 사용 하거나 다른 변수 이름을 사용 합니다.

자세한 내용은 [pack](../../preprocessor/pack.md) 하 고 [__alignof 연산자](../../cpp/alignof-operator.md)합니다.

## <a name="example"></a>예제

형식을 정의 하는 첫 번째 파일입니다.

```
// C4742a.c
// compile with: /c
struct X {
   char x, y, z, w;
} global;
```

## <a name="example"></a>예제

다음 샘플에서는 C4742 오류가 발생 합니다.

```
// C4742b.c
// compile with: C4742a.c /W1 /GL
// C4742 expected
extern struct X {
   int a;
} global;

int main() {
   global.a = 0;
}
```
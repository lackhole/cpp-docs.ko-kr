---
title: 컴파일러 경고 (수준 1) C4377
ms.date: 11/04/2016
f1_keywords:
- C4377
helpviewer_keywords:
- C4377
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
ms.openlocfilehash: 30e2ecb1d5e0de290c028cdfb53c7df831a732b4
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966457"
---
# <a name="compiler-warning-level-1-c4377"></a>컴파일러 경고 (수준 1) C4377

네이티브 형식은 기본적으로 private입니다. -d1PrivateNativeTypes는 사용 되지 않습니다.

이전 릴리스에서는 어셈블리의 네이티브 형식이 기본적으로 public이 고 문서화 되지 않은 내부 컴파일러 옵션 ( **/d1PrivateNativeTypes**)을 사용 하 여 전용으로 설정 했습니다.

모든 형식, 네이티브 및 CLR은 이제 기본적으로 어셈블리에서 private 이므로 **/d1PrivateNativeTypes** 가 더 이상 필요 하지 않습니다.

## <a name="example"></a>예제

다음 샘플에서는 C4377를 생성 합니다.

```cpp
// C4377.cpp
// compile with: /clr /d1PrivateNativeTypes /W1
// C4377 warning expected
int main() {}
```
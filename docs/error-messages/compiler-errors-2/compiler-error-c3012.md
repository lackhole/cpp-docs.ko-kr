---
title: 컴파일러 오류 C3012
ms.date: 11/04/2016
f1_keywords:
- C3012
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
ms.openlocfilehash: 9fe0ac7d3637cad3a5571c4631345dac1a0021bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386735"
---
# <a name="compiler-error-c3012"></a>컴파일러 오류 C3012

> '*내장*': 내장 함수 병렬 영역 내부에서는 직접 사용할 수 없습니다

 [컴파일러 내장](../../intrinsics/compiler-intrinsics.md) 함수는 `omp parallel` 지역에서 사용할 수 없습니다. 이 문제를 해결 하려면 지역에서 내장 함수를 이동 하거나 비 내장 항목으로 바꾸세요.

## <a name="example"></a>예제

다음 샘플 C3012를 생성 및이 해결 하는 방법을 보여 줍니다.

```cpp
// C3012.cpp
// compile with: /openmp
#ifdef __cplusplus
extern "C" {
#endif
void* _ReturnAddress();
#ifdef __cplusplus
}
#endif

int main()
{
   #pragma omp parallel
   {
      _ReturnAddress();   // C3012
   }
   _ReturnAddress();      // OK
}
```
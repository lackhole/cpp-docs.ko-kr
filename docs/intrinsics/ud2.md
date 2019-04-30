---
title: __ud2
ms.date: 11/04/2016
f1_keywords:
- __ud2
helpviewer_keywords:
- UD2 instruction
- __ud2 intrinsic
ms.assetid: 0831cd5a-8b65-402e-bb57-11e1d5d7ffd2
ms.openlocfilehash: a36ab5c25ac9138b2a4d6810cc2a339e534f1695
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390180"
---
# <a name="ud2"></a>__ud2

**Microsoft 전용**

정의 되지 않은 명령을 생성합니다.

## <a name="syntax"></a>구문

```
void __ud2();
```

## <a name="remarks"></a>설명

프로세서 정의 되지 않은 명령을 실행 하는 경우 잘못 된 opcode가 예외를 발생 시킵니다.

합니다 `__ud2` 함수는 동일 합니다 `UD2` 컴퓨터 명령 및 커널 모드 에서만 사용할 수 있습니다. 자세한 내용은 문서에 대해 검색 "Intel 아키텍처 소프트웨어 개발자 설명서 볼륨 2: 명령 집합 참조를 "에 [Intel Corporation](https://software.intel.com/articles/intel-sdm) 사이트입니다.

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|
|---------------|------------------|
|`__ud2`|x86, x64|

**헤더 파일** \<intrin.h >

**Microsoft 전용 종료**

## <a name="example"></a>예제

다음 예제에서는 예외가 발생 하는 정의 되지 않은 명령을 실행 합니다. 그런 다음 예외 처리기 하나는 0 개에서 반환 코드를 변경합니다.

```
// __ud2_intrinsic.cpp
#include <stdio.h>
#include <intrin.h>
#include <excpt.h>
// compile with /EHa

int main() {

// Initialize the return code to 0.
int ret = 0;

// Attempt to execute an undefined instruction.
  printf("Before __ud2(). Return code = %d.\n", ret);
  __try {
  __ud2();
  }

// Catch any exceptions and set the return code to 1.
  __except(EXCEPTION_EXECUTE_HANDLER){
  printf("  In the exception handler.\n");
  ret = 1;
  }

// Report the value of the return code.
  printf("After __ud2().  Return code = %d.\n", ret);
  return ret;
}
```

```Output
Before __ud2(). Return code = 0.
  In the exception handler.
After __ud2().  Return code = 1.
```

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)
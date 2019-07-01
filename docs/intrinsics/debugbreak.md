---
title: __debugbreak
ms.date: 11/04/2016
f1_keywords:
- __debugbreak_cpp
- __debugbreak
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
ms.openlocfilehash: 97932dfe0e187a13b72ae5fe70d761224721c3ff
ms.sourcegitcommit: 1acb6755e11379026a96f63facac4d33f4dc47ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/21/2019
ms.locfileid: "67314249"
---
# <a name="debugbreak"></a>__debugbreak

**Microsoft 전용**

코드에서 중단점이 발생하며 사용자에게 디버거를 실행하라는 메시지가 표시됩니다.

## <a name="syntax"></a>구문

```
void __debugbreak();
```

## <a name="requirements"></a>요구 사항

|내장 함수|아키텍처|헤더|
|---------------|------------------|------------|
|`__debugbreak`|x86, x64, ARM, ARM64|\<intrin.h>|

## <a name="remarks"></a>설명

`__debugbreak` 컴파일러 내장 마찬가지로 [DebugBreak](https://msdn.microsoft.com/library/windows/desktop/ms679297.aspx), 중단점을 발생 시키는 이식 가능한 Win32 방법이 있습니다.

> [!NOTE]
>  사용 하 여 컴파일하면 **/clr**를 포함 하는 함수 `__debugbreak` MSIL로 컴파일됩니다. `asm int 3`은 함수를 네이티브로 컴파일하도록 합니다. 자세한 내용은 [__asm](../assembler/inline/asm.md)합니다.

예를 들어:

```
main() {
   __debugbreak();
}
```

위의 예는 아래 예와 유사합니다.

```
main() {
   __asm {
      int 3
   }
}
```

x86 컴퓨터의 경우

ARM64에 `__debugbreak` 명령으로 내장 함수는 컴파일된 `brk #0xF000`합니다.

이 루틴은 내장 루틴으로만 사용할 수 있습니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 내장 함수](../intrinsics/compiler-intrinsics.md)<br/>
[C++ 키워드](../cpp/keywords-cpp.md)

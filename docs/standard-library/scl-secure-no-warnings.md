---
title: _SCL_SECURE_NO_WARNINGS
ms.date: 11/04/2016
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
ms.openlocfilehash: 77c60aed511fc3dbbea2d74e83e36dae735dcb0e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348310"
---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS

안전 하지 않은 메서드 중 하나를 호출 합니다 C++ 표준 라이브러리에서 결과 [컴파일러 경고 (수준 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)합니다. 이 경고를 비활성화 하려면 코드에서 매크로 _SCL_SECURE_NO_WARNINGS를 정의 합니다.

```cpp
#define _SCL_SECURE_NO_WARNINGS
```

미리 컴파일된 헤더를 사용 하는 경우는 모든 C 런타임 라이브러리 또는 표준 라이브러리 헤더를 포함 하기 전에 미리 컴파일된 헤더 파일에서이 지시어를 배치 합니다. 추가 하면 개별 원본 코드 파일에 미리 컴파일된 헤더 파일을 포함 하기 전에, 컴파일러에서 무시 됩니다.

## <a name="remarks"></a>설명

C4996 경고를 비활성화하는 다른 방법은 다음과 같습니다.

- [/D(전처리기 정의)](../build/reference/d-preprocessor-definitions.md) 컴파일러 옵션을 사용합니다.

   > cl [다른 컴파일러 옵션] /D_SCL_SECURE_NO_WARNINGS myfile.cpp

- [/w](../build/reference/compiler-option-warning-level.md) 컴파일러 옵션을 사용합니다.

   > cl /wd4996 [other compiler options] myfile.cpp

- [#pragma warning](../preprocessor/warning.md) 경고를 사용합니다.

   ```cpp
   #pragma warning(disable:4996)
   ```

**/w\<l>\<n>** 컴파일러 옵션을 사용하여 경고 C4996의 수준을 수동으로 변경할 수도 있습니다. 예를 들어 C4996 경고를 수준 4로 설정하려면 다음 코드를 사용합니다.

> cl /w44996 [other compiler options] myfile.cpp

자세한 내용은 [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX(경고 수준)](../build/reference/compiler-option-warning-level.md)를 참조하세요.

## <a name="see-also"></a>참고자료

[안전한 라이브러리: C++ 표준 라이브러리](../standard-library/safe-libraries-cpp-standard-library.md)<br/>

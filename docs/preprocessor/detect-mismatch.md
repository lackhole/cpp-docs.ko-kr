---
title: detect_mismatch
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
ms.openlocfilehash: 42a3ba61cefe3b2db01aef24b802e3a51fed55d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62389335"
---
# <a name="detectmismatch"></a>detect_mismatch
레코드를 개체에 배치합니다. 링커는 이러한 레코드를 검사하여 잠재적인 불일치를 확인합니다.

## <a name="syntax"></a>구문

```
#pragma detect_mismatch("name", "value")
```

## <a name="remarks"></a>설명

프로젝트를 링크할 때 `LNK2038`은 동일하지만 `name`가 서로 다른 두 개체가 프로젝트에 포함된 경우 링커는 `value` 오류를 발생시킵니다. 이 pragma를 사용하여 일치하지 않는 개체 파일이 링크되는 것을 방지할 수 있습니다.

이름과 값은 둘 다 문자열 리터럴이며 이스케이프 문자 및 연결과 관련하여 문자열 리터럴에 대한 규칙을 준수합니다. 대 소문자를 구분 하며 쉼표, 등호, 따옴표를 포함할 수 없습니다 또는 **null** 문자입니다.

## <a name="example"></a>예제

이 예제에서는 같은 버전 레이블에 대한 버전 번호가 서로 다른 두 파일을 만듭니다.

```cpp
// pragma_directive_detect_mismatch_a.cpp
#pragma detect_mismatch("myLib_version", "9")
int main ()
{
   return 0;
}

// pragma_directive_detect_mismatch_b.cpp
#pragma detect_mismatch("myLib_version", "1")
```

`cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp` 명령줄을 사용하여 이러한 파일을 둘 다 컴파일하는 경우 `LNK2038` 오류가 발생합니다.

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

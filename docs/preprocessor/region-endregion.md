---
title: region, endregion pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.endregion
- endregion_CPP
- region_CPP
- vc-pragma.region
helpviewer_keywords:
- pragmas, region
- pragmas, endregion
- endregion pragma
- region pragma
ms.assetid: c697f807-622f-4796-851b-68a42bbecd84
ms.openlocfilehash: 4a01e04582ac81d678aa0702945c62ee974a4428
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222382"
---
# <a name="region-endregion-pragmas"></a>region, endregion pragma

`#pragma region`Visual Studio Code 편집기의 [개요 기능](/visualstudio/ide/outlining) 을 사용할 때 확장 하거나 축소할 수 있는 코드 블록을 지정할 수 있습니다.

## <a name="syntax"></a>구문

> **#pragma 지역** *이름*\
> **#pragma endregion** *설명*

### <a name="parameters"></a>매개 변수

*주석의*\
필드 코드 편집기에 표시 되는 주석입니다.

*이름의*\
필드 영역 이름입니다. 이 이름은 코드 편집기에 표시 됩니다.

## <a name="remarks"></a>설명

`#pragma endregion``#pragma region` 블록의 끝을 표시 합니다.

블록 `#region` 은 `#pragma endregion` 지시문으로 종료 해야 합니다.

## <a name="example"></a>예제

```cpp
// pragma_directives_region.cpp
#pragma region Region_1
void Test() {}
void Test2() {}
void Test3() {}
#pragma endregion Region_1

int main() {}
```

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 __pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)

---
title: region, endregion
ms.date: 10/18/2018
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
ms.openlocfilehash: c73a90aa2be83d643b74dde4645081e89da3ff73
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59037933"
---
# <a name="region-endregion"></a>region, endregion

`#pragma region` 확장 하거나 사용 하는 경우 축소할 수 있는 코드 블록을 지정할 수 있습니다 합니다 [개요 기능](/visualstudio/ide/outlining) Visual Studio 코드 편집기입니다.

## <a name="syntax"></a>구문

```
#pragma region name
#pragma endregion comment
```

### <a name="parameters"></a>매개 변수

*comment*<br/>
(선택 사항) 코드 편집기에 표시 되는 주석입니다.

*name*<br/>
(선택 사항) 영역의 이름입니다.  이 이름은 코드 편집기에 표시됩니다.

## <a name="remarks"></a>설명

`#pragma endregion` 끝을 표시 한 `#pragma region` 블록입니다.

A `#region` 블록으로 종결 되어야 합니다 `#pragma endregion`합니다.

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

[Pragma 지시문 및 __Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
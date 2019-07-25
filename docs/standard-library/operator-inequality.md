---
title: operator!=
ms.date: 11/04/2016
f1_keywords:
- std::!=
- '!='
- std::operator!=
- std.operator!=
- std.!=
- operator!=
helpviewer_keywords:
- '!= operator'
- operator!=
- operator !=
ms.assetid: ef2be7f0-1c94-4edc-b65c-731fddd519f4
ms.openlocfilehash: 1214dd7d5034b80b14f8dd1422aa1a3b8a253023
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447645"
---
# <a name="operator"></a>operator!=

> [!NOTE]
> 이 항목은 Microsoft C++ 설명서에서 C++ 표준 라이브러리에 사용 되는 컨테이너의 작동 하지 않는 예제로 작성 되었습니다. 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.

`operator!=`를 오버로드하여 템플릿 클래스 [Container](../standard-library/sample-container-class.md)의 개체 두 개를 비교합니다.

## <a name="syntax"></a>구문

```cpp
template <class Ty>
bool operator!=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>반환 값

`!(left == right)`를 반환합니다.

## <a name="see-also"></a>참고자료

[\<sample container>](../standard-library/sample-container.md)

---
title: Container Class::erase
ms.date: 11/04/2016
helpviewer_keywords:
- erase method
ms.assetid: abc091c5-5a80-4bd8-93a8-a2d9bde2efec
ms.openlocfilehash: 11e13fc74de779076b40ba338a21a6736eb04e06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62211058"
---
# <a name="container-classerase"></a>Container Class::erase

> [!NOTE]
> 이 항목은 C++ 표준 라이브러리에서 사용되는 작동하지 않는 컨테이너 예제로 Visual C++ 설명서에 포함되어 있습니다. 자세한 내용은 [C++ 표준 라이브러리 컨테이너](../standard-library/stl-containers.md)를 참조하세요.

요소를 지웁니다.

## <a name="syntax"></a>구문

```

    iterator erase(
    iterator _Where);

iterator erase(
    iterator first,
    iterator last);
```

## <a name="remarks"></a>설명

가 가리키는 제어 되는 시퀀스의 요소를 제거 하는 첫 번째 멤버 함수 *_Where*합니다. 두 번째 멤버 함수는 [`first`, `last`]의 범위에서 제어되는 시퀀스의 요소를 제거합니다. 둘 다 제거된 요소 다음에 남아 있는 첫 번째 요소를 지정하는 반복기를 반환하거나, 이러한 요소가 없는 경우 [end](../standard-library/container-class-end.md)를 반환합니다.

복사 작업에서 예외를 throw하는 경우에만 멤버 함수는 예외를 throw합니다.

## <a name="see-also"></a>참고자료

[샘플 컨테이너 클래스](../standard-library/sample-container-class.md)<br/>

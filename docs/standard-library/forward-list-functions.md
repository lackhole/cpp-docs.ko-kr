---
title: '&lt;forward_list&gt; 함수'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: b425461f1428470b04a525efdd9a702ae038a283
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159836"
---
# <a name="ltforwardlistgt-functions"></a>&lt;forward_list&gt; 함수

||
|-|
|[swap](#swap)|

## <a name="swap"></a>  swap

두 정방향 목록의 요소를 교환합니다.

```cpp
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*left*|`forward_list` 형식의 개체입니다.|
|*right*|`forward_list` 형식의 개체입니다.|

### <a name="remarks"></a>설명

이 템플릿 함수는 `left.swap(right)`를 실행합니다.

## <a name="see-also"></a>참고자료

[<forward_list>](../standard-library/forward-list.md)<br/>

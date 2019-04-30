---
title: '&lt;memory&gt; 열거형'
ms.date: 11/04/2016
f1_keywords:
- memory/std::pointer_safety
ms.assetid: b9be0a7b-0beb-40b2-8183-911de371c6b9
ms.openlocfilehash: 5c5f87905b772ef277a72ef11defef8cb1001661
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412841"
---
# <a name="ltmemorygt-enums"></a>&lt;memory&gt; 열거형

||
|-|
|[pointer_safety](#pointer_safety)|

## <a name="pointer_safety"></a>  pointer_safety 열거형

`get_pointer_safety`에서 반환할 수 있는 값의 열거형입니다.

class pointer_safety { relaxed, preferred, strict };

### <a name="remarks"></a>설명

범위 **enum** 에서 반환 될 수 있는 값을 정의 `get_pointer_safety()`:

`relaxed` - 안전하게 파생되지 않은 포인터(선언되거나 할당된 개체에 대한 포인터)를 안전하게 파생된 포인터와 동일하게 처리합니다.

`preferred` - 이전 설명과 같지만 안전하게 파생되지 않은 포인터를 역참조해서는 안 됩니다.

`strict` - 안전하게 파생되지 않은 포인터를 안전하게 파생된 포인터와 다르게 처리할 수 있습니다.

## <a name="see-also"></a>참고자료

[\<memory>](../standard-library/memory.md)<br/>

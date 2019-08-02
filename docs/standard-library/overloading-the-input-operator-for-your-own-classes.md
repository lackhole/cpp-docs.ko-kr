---
title: 고유 클래스에 대해 &gt;&gt; 연산자 오버로드
ms.date: 11/04/2016
helpviewer_keywords:
- operator>>
- operator>>, overloading for your own classes
- operator >>, overloading for your own classes
ms.assetid: 40dab4e0-3f97-4745-9cc8-b86e740fa246
ms.openlocfilehash: 672dfb7ec40b2f18cbde0adc92522d3194a5e738
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450132"
---
# <a name="overloading-the-gtgt-operator-for-your-own-classes"></a>고유 클래스에 대해 &gt;&gt; 연산자 오버로드

입력 스트림은 표준 형식에 대해 추출(`>>`) 연산자를 사용합니다. 고유 형식용으로 유사한 추출 연산자를 작성할 수 있으며, 이 경우 공백을 정확하게 사용해야 합니다.

앞에서 살펴보았던 `Date` 클래스에 대한 추출 연산자의 한 예가 아래에 나와 있습니다.

```cpp
istream& operator>> (istream& is, Date& dt)
{
    is>> dt.mo>> dt.da>> dt.yr;
    return is;
}
```

## <a name="see-also"></a>참고자료

[입력 스트림](../standard-library/input-streams.md)

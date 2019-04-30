---
title: 변경할 수 있는 데이터 멤버 (C++)
ms.date: 11/04/2016
f1_keywords:
- mutable_cpp
helpviewer_keywords:
- mutable keyword [C++]
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
ms.openlocfilehash: 8d592eb97f70bfc26c075317c57ec4d5c78e3956
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301593"
---
# <a name="mutable-data-members-c"></a>변경할 수 있는 데이터 멤버 (C++)

이 키워드는 클래스에서 static도 const도 아닌 데이터 멤버에만 적용할 수 있습니다. 데이터 멤버를 **mutable**로 선언하면, **const** 멤버 함수에서 이 데이터 멤버에 대한 값 할당 작업이 허용됩니다.

## <a name="syntax"></a>구문

```
mutable member-variable-declaration;
```

## <a name="remarks"></a>설명

예를 들어, 다음 코드는 `m_accessCount`가 **mutable**로 선언되었기 때문에 오류 없이 컴파일되고, 따라서 `GetFlag`가 const 멤버 함수라도 `GetFlag`에서 이를 변경할 수 있습니다.

```cpp
// mutable.cpp
class X
{
public:
   bool GetFlag() const
   {
      m_accessCount++;
      return m_flag;
   }
private:
   bool m_flag;
   mutable int m_accessCount;
};

int main()
{
}
```

## <a name="see-also"></a>참고 항목

[C++ 키워드](../cpp/keywords-cpp.md)
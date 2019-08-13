---
title: bad_optional_access 클래스
ms.date: 08/06/2019
f1_keywords:
- optional/std::bad_optional_access
ms.openlocfilehash: 043b0360c7e0be48267c8f406dbfea50eeb5a8e3
ms.sourcegitcommit: 16c0392fc8d96e814c3a40b0c5346d7389aeb525
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2019
ms.locfileid: "68957093"
---
# <a name="bad_optional_access-class"></a>bad_optional_access 클래스

값을 포함 하지 않는 `optional` 개체의 값에 대 한 액세스를 시도 하는 상황을 보고 하는 예외로 throw 되는 개체의 형식을 정의 합니다.

## <a name="syntax"></a>구문

```cpp
class bad_optional_access : public exception
{
public:
    bad_optional_access() noexcept;
    bad_optional_access(const bad_optional_access&) noexcept;
    bad_optional_access& operator=(const bad_optional_access&) noexcept;
    const char* what() const noexcept override;
};
```

## <a name="see-also"></a>참고자료

[\<선택적 >](optional.md)\
[선택적 클래스](optional-class.md)

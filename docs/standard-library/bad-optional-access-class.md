---
title: bad_optional_access 클래스
ms.date: 11/04/2016
f1_keywords:
- optional/std::bad_optional_access
ms.assetid: 89a3b805-ab60-4858-b772-5855130c11b1
ms.openlocfilehash: f898d1e30dd173339192bdb3b75581d12b62fca7
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68269145"
---
# <a name="badoptionalaccess-class"></a>bad_optional_access 클래스

값에 액세스 하려고 할 있는 상황을 보고 하는 예외 throw 되는 개체의 형식을 정의 하는 `optional` 값을 포함 하지 않는 개체입니다.

## <a name="syntax"></a>구문

```cpp
class bad_optional_access : public exception
{
    public: bad_optional_access();
};
```

---
title: bad_any_cast 클래스
ms.date: 04/04/2019
f1_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
helpviewer_keywords:
- any/std::bad_any_cast
- any/std::bad_any_cast::what
ms.openlocfilehash: 5172281d1918a8b4ac33bcf412bf4be82b04ef56
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268685"
---
# <a name="badanycast-class"></a>bad_any_cast 클래스

실패 한 작업에서 throw 되는 개체 `any_cast`합니다.

## <a name="syntax"></a>구문

```cpp
class bad_any_cast
```

### <a name="member-functions"></a>멤버 함수

|||
|-|-|
|[what](#what)|형식을 반환합니다.|

## <a name="what"></a> 새로운

형식을 반환합니다.

```cpp
const char* what() const noexcept override;
```

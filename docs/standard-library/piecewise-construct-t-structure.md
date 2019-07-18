---
title: piecewise_contruct_t 구조
ms.date: 11/04/2016
f1_keywords:
- utility/std::piecewise_contruct_t
helpviewer_keywords:
- piecewise_contruct_t class
- piecewise_contruct_t structure
ms.openlocfilehash: 6a9a6af97ca5c7751d64cd1fa70c9d9eba87da7c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68268365"
---
# <a name="piecewisecontructt-structure"></a>piecewise_contruct_t 구조

구조체 `piecewise_construct_t` 빈 구조체 형식인 별도 생성자 및 함수 오버 로드를 유지 하는 데 사용 합니다. 특히 `pair` 사용 하 여 생성자가 `piecewise_construct_t` 첫 번째 인수로 뒤에 두 개의 `tuple` 인수입니다.

## <a name="syntax"></a>구문

```cpp
struct piecewise_construct_t { explicit piecewise_construct_t() = default; };

inline constexpr piecewise_construct_t piecewise_construct{};
```

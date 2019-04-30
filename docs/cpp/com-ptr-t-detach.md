---
title: _com_ptr_t::Detach
ms.date: 11/04/2016
f1_keywords:
- _com_ptr_t::Detach
helpviewer_keywords:
- Detach method [C++]
ms.assetid: 0652053e-af37-44e9-a278-2522212ebfed
ms.openlocfilehash: affaefd8af4802836733587af62977171ba01410
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154970"
---
# <a name="comptrtdetach"></a>_com_ptr_t::Detach

**Microsoft 전용**

캡슐화된 인터페이스 포인터를 추출하고 반환합니다.

## <a name="syntax"></a>구문

```
Interface* Detach( ) throw( );
```

## <a name="remarks"></a>설명

추출 및 캡슐화 된 인터페이스 포인터를 반환 하 고 NULL로 캡슐화 된 포인터 저장소를 지웁니다. 이 작업을 통해 인터페이스 포인터의 캡슐화를 제거합니다. 호출 하는 것 `Release` 반환 된 인터페이스 포인터에 대 한 합니다.

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[_com_ptr_t 클래스](../cpp/com-ptr-t-class.md)
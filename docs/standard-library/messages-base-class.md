---
title: messages_base 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_base
helpviewer_keywords:
- messages_base class
ms.assetid: 9aad38c6-4c13-445d-b096-364bd0836efb
ms.openlocfilehash: 79b6cb5f0b0c219e959f53fdc667f4c8af273cef
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451843"
---
# <a name="messagesbase-class"></a>messages_base 클래스

기본 클래스는 메시지 카탈로그에 대 한 **int** 형식을 설명 합니다.

## <a name="syntax"></a>구문

```cpp
struct messages_base : locale::facet {
    typedef int catalog;
    explicit messages_base(size_t _Refs = 0)
};
```

## <a name="remarks"></a>설명

형식 카탈로그는 messages:: [do_open](../standard-library/messages-class.md#do_open)에서 가능한 반환 값을 설명 하는 **int** 형식의 동의어입니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

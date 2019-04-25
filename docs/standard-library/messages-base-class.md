---
title: messages_base 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_base
helpviewer_keywords:
- messages_base class
ms.assetid: 9aad38c6-4c13-445d-b096-364bd0836efb
ms.openlocfilehash: 750c9f36ce7f96a065e0e29111ea379a48595328
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167766"
---
# <a name="messagesbase-class"></a>messages_base 클래스

설명 하는 기본 클래스는 **int** 카탈로그에 대 한 메시지의 형식입니다.

## <a name="syntax"></a>구문

```cpp
struct messages_base : locale::facet {
    typedef int catalog;
    explicit messages_base(size_t _Refs = 0)
};
```

## <a name="remarks"></a>설명

형식 카탈로그 형식에 대 한 동의어가 **int** 설명 하는 메시지에서 가능한 반환 값:: [do_open](../standard-library/messages-class.md#do_open)합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

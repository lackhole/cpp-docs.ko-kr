---
title: future_error 클래스
ms.date: 11/04/2016
f1_keywords:
- future/std::future_error
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
ms.openlocfilehash: ed3f9d63c45d0e185e3e1476094736d132822173
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68447354"
---
# <a name="futureerror-class"></a>future_error 클래스

[future](../standard-library/future-class.md) 개체를 관리하는 형식의 메서드에서 throw될 수 있는 예외 개체를 설명합니다.

## <a name="syntax"></a>구문

```cpp
class future_error : public logic_error {
public:
    future_error(error_code code);

const error_code& code() const throw();

const char *what() const throw();

};
```

## <a name="requirements"></a>요구 사항

**헤더:** \<이후 >

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[헤더 파일 참조](../standard-library/cpp-standard-library-header-files.md)\
[logic_error 클래스](../standard-library/logic-error-class.md)\
[error_code 클래스](../standard-library/error-code-class.md)

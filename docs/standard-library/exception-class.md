---
title: exception 클래스
ms.date: 11/04/2016
f1_keywords:
- exception
helpviewer_keywords:
- exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
ms.openlocfilehash: 90906469e923d29dd886930bd36944e4292bd9cd
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246076"
---
# <a name="exception-class"></a>exception 클래스

이 클래스는 특정 식과 C++ 표준 라이브러리로 throw된 모든 예외에 대한 기본 클래스로 사용됩니다.

## <a name="syntax"></a>구문

```cpp
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
};
```

## <a name="remarks"></a>설명

특히 이 기본 클래스는 [\<stdexcept>](../standard-library/stdexcept.md)에 정의된 표준 예외 클래스의 루트입니다. `what`에서 반환된 C 문자열 값은 기본 생성자에 의해서는 지정되지 않지만 특정 파생 클래스의 생성자에 의해 구현이 정의된 C 문자열로 정의될 수 있습니다. 멤버 함수는 예외를 발생시키지 않습니다.

합니다 **int** 매개 변수를 사용 하면 메모리를 할당 되는 지정할 수 있습니다. 값을 **int** 무시 됩니다.

> [!NOTE]
> 생성자 `exception(const char* const &message)` 및 `exception(const char* const &message, int)`는 C++ 표준 라이브러리에 대한 Microsoft 확장입니다.

## <a name="example"></a>예제

`exception` 클래스에서 상속된 표준 예외 클래스 사용의 예는 [\<stdexcept>](../standard-library/stdexcept.md)를 참조하세요.

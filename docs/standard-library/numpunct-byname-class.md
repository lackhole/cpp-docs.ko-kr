---
title: numpunct_byname 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct_byname
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
ms.openlocfilehash: da9259df8c527e44a4adea3a53be31b3c3ffc10b
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687604"
---
# <a name="numpunct_byname-class"></a>numpunct_byname 클래스

파생 된 클래스 템플릿은 숫자 및 부울 식의 서식 지정 및 문장 부호를 사용할 수 있도록 지정 된 로캘의 `numpunct` 패싯으로 사용할 수 있는 개체를 설명 합니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType>
class numpunct_byname : public numpunct<Elem> {
public:
    explicit numpunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit numpunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~numpunct_byname();

};
```

## <a name="remarks"></a>주의

해당 동작은 [명명된](../standard-library/locale-class.md#name) 로캘 `_Locname`에 의해 결정됩니다. 생성자는 [numpunct](../standard-library/numpunct-class.md#numpunct)\<CharType>( `_Refs`)를 통해 해당 기준 개체를 초기화합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

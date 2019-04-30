---
title: numpunct_byname 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct_byname
helpviewer_keywords:
- numpunct_byname class
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
ms.openlocfilehash: 64e8918b052b05088ff48aefb0f0f9ab8c6df586
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371494"
---
# <a name="numpunctbyname-class"></a>numpunct_byname 클래스

이 파생된 템플릿 클래스는 지정된 로캘의 `numpunct` 패싯으로 사용하여 숫자 및 부울 식의 문장 부호 서식을 지정할 수 있는 개체를 설명합니다.

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

## <a name="remarks"></a>설명

해당 동작은 [명명된](../standard-library/locale-class.md#name) 로캘 `_Locname`에 의해 결정됩니다. 생성자는 [numpunct](../standard-library/numpunct-class.md#numpunct)\<CharType>( `_Refs`)를 통해 해당 기준 개체를 초기화합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

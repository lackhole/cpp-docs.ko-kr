---
title: moneypunct_byname 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::moneypunct_byname
helpviewer_keywords:
- moneypunct_byname class
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
ms.openlocfilehash: c687bc870e4d78cfe9174eb04ea09c34d6a9c955
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687663"
---
# <a name="moneypunct_byname-class"></a>moneypunct_byname 클래스

지정 된 로캘의 `moneypunct` 패싯으로 사용 하 여 통화 입력 필드 또는 통화 출력 필드의 서식을 지정할 수 있는 개체를 설명 하는 파생 클래스 템플릿입니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType, bool Intl = false>
class moneypunct_byname : public moneypunct<CharType, Intl>
{
public:
    explicit moneypunct_byname(
    const char* _Locname,
    size_t _Refs = 0);

    explicit moneypunct_byname(
    const string& _Locname,
    size_t _Refs = 0);

protected:
    virtual ~moneypunct_byname();

};
```

## <a name="remarks"></a>주의

해당 동작은 명명된 로캘 `_Locname`에 따라 결정됩니다. 각 생성자는 [moneypunct](../standard-library/moneypunct-class.md#moneypunct)\<CharType, Intl>( `_Refs`)를 통해 해당 기준 개체를 초기화합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참조

[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

---
title: ctype&lt;char&gt; 클래스
ms.date: 11/04/2016
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
ms.openlocfilehash: adaad8f76de5b712aea13794ef2d7b9a096fb8ef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394158"
---
# <a name="ctypeltchargt-class"></a>ctype&lt;char&gt; 클래스

클래스는 템플릿 클래스의 명시적 특수화 `ctype\<CharType>` 입력할 **char**, 형식 문자의 다양 한 속성을 특성화 하기 위해 로캘 패싯으로 사용할 수 있는 개체에 설명 **char**.

## <a name="syntax"></a>구문

```cpp
template <>
class ctype<char>
: public ctype_base
{
public:
    typedef char _Elem;
    typedef _Elem char_type;
    bool is(
    mask _Maskval,
    _Elem _Ch) const;

    const _Elem* is(
    const _Elem* first,
    const _Elem* last,
    mask* dest) const;

    const _Elem* scan_is(
    mask _Maskval,
    const _Elem* first,
    const _Elem* last) const;

    const _Elem* scan_not(
    mask _Maskval,
    const _Elem* first,
    const _Elem* last) const;

    _Elem tolower(
    _Elem _Ch) const;

    const _Elem* tolower(
    _Elem* first,
    const _Elem* last) const;

    _Elem toupper(
    _Elem _Ch) const;

    const _Elem* toupper(
    _Elem* first,
    const _Elem* last) const;

    _Elem widen(
    char _Byte) const;

    const _Elem* widen(
    const char* first,
    const char* last,
    _Elem* dest) const;

    const _Elem* _Widen_s(
    const char* first,
    const char* last,
    _Elem* dest,
    size_t dest_size) const;

    _Elem narrow(
    _Elem _Ch,
    char _Dflt = '\0') const;

    const _Elem* narrow(
    const _Elem* first,
    const _Elem* last,
    char _Dflt,
    char* dest) const;

    const _Elem* _Narrow_s(
    const _Elem* first,
    const _Elem* last,
    char _Dflt,
    char* dest,
    size_t dest_size) const;

    static locale::id& id;
    explicit ctype(
    const mask* _Table = 0,
    bool _Deletetable = false,
    size_t _Refs = 0);

protected:
    virtual ~ctype();
//other protected members
};
```

## <a name="remarks"></a>설명

명시적 특수화는 다음과 같은 여러 가지 면에서 템플릿 클래스와 다릅니다.

- Ctype 클래스의 개체 < `char`>는 ctype 마스크 테이블의 첫 번째 요소를 배열 uchar_max + 1 개 요소 형식의 포인터를 저장 `ctype_base::mask`합니다. 또한 ctype\< **Elem**> 개체가 삭제된 경우 배열을 삭제해야 할지(`operator delete[]`를 사용하여) 여부를 나타내는 부울 개체도 저장합니다.

- 유일한 공용 생성자를 지정할 수 있습니다 `tab`, ctype 마스크 테이블 및 `del`, 배열의 되어야 하면 true 인 부울 개체 삭제 ctype < `char`> 참조-카운트 뿐만 아니라 개체가 제거 될 매개 변수 참조입니다.

- 보호 된 멤버 함수 `table` 저장 된 ctype 마스크 테이블을 반환 합니다.

- 정적 멤버 개체 `table_size` ctype 마스크 테이블의 최소 요소 수를 지정 합니다.

- 보호 된 정적 멤버 함수 `classic_table`(반환 ctype 마스크 테이블 "C" 로캘에 적합 한 합니다.

- 보호된 가상 멤버 함수 [do_is](../standard-library/ctype-class.md#do_is), [do_scan_is](../standard-library/ctype-class.md#do_scan_is) 또는 [do_scan_not](../standard-library/ctype-class.md#do_scan_not)이 없습니다. 해당 공용 멤버 함수는 동일한 작업을 자체적으로 수행합니다.

멤버 함수 [do_narrow](../standard-library/ctype-class.md#do_narrow) 및 [do_widen](../standard-library/ctype-class.md#do_widen)은 변경되지 않은 요소를 복사합니다.

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="see-also"></a>참고자료

[facet 클래스](locale-class.md#facet_class)<br/>
[ctype_base 클래스](../standard-library/ctype-base-class.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

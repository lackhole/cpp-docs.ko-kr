---
title: messages 클래스
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages
- xlocmes/std::messages::char_type
- xlocmes/std::messages::string_type
- xlocmes/std::messages::close
- xlocmes/std::messages::do_close
- xlocmes/std::messages::do_get
- xlocmes/std::messages::do_open
- xlocmes/std::messages::get
- xlocmes/std::messages::open
helpviewer_keywords:
- std::messages [C++]
- std::messages [C++], char_type
- std::messages [C++], string_type
- std::messages [C++], close
- std::messages [C++], do_close
- std::messages [C++], do_get
- std::messages [C++], do_open
- std::messages [C++], get
- std::messages [C++], open
ms.assetid: c4c71f40-4f24-48ab-9f7c-daccd8d5bd83
ms.openlocfilehash: 704ee2ce40b4026cc066213181c96cf0f744d152
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687681"
---
# <a name="messages-class"></a>messages 클래스

클래스 템플릿은 지정 된 로캘에 대 한 국제화 된 메시지의 카탈로그에서 지역화 된 메시지를 검색 하기 위해 로캘 패싯으로 사용할 수 있는 개체를 설명 합니다.

현재 메시지 클래스가 구현되는 동안 메시지가 없습니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType>
class messages : public messages_base;
```

### <a name="parameters"></a>매개 변수

*Chartype* \
로캘의 문자를 인코딩하기 위해 프로그램 내 사용하는 형식입니다.

## <a name="remarks"></a>주의

모든 로캘 패싯과 마찬가지로, 고정 개체 ID에는 초기값 0이 저장되어 있습니다. 저장된 값에 액세스를 처음 시도하면 **id**에 고유한 양수 값이 저장됩니다.

이 패싯은 기본적으로 기본 클래스 messages_base에 정의된 메시지의 카탈로그를 열고, 필요한 정보를 검색하며, 카탈로그를 닫습니다.

### <a name="constructors"></a>생성자

|생성자|설명|
|-|-|
|[messages](#messages)|메시지 패싯 생성자 함수입니다.|

### <a name="typedefs"></a>형식 정의

|형식 이름|설명|
|-|-|
|[char_type](#char_type)|메시지를 표시하는 데 사용하는 문자 형식입니다.|
|[string_type](#string_type)|`basic_string` 형식의 문자가 포함된 `CharType` 형식의 문자열을 설명하는 형식입니다.|

### <a name="member-functions"></a>멤버 함수

|멤버 함수|설명|
|-|-|
|[close](#close)|메시지 카탈로그를 닫습니다.|
|[do_close](#do_close)|메시지 카탈로그를 닫기 위해 호출하는 가상 함수입니다.|
|[do_get](#do_get)|메시지 카탈로그를 검색하기 위해 호출하는 가상 함수입니다.|
|[do_open](#do_open)|메시지 카탈로그를 열기 위해 호출하는 가상 함수입니다.|
|[get](#get)|메시지 카탈로그를 불러옵니다.|
|[open](#open)|메시지 카탈로그를 엽니다.|

## <a name="requirements"></a>요구 사항

**헤더:** \<locale>

**네임스페이스:** std

## <a name="char_type"></a>  messages::char_type

메시지를 표시하는 데 사용하는 문자 형식입니다.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>주의

이 형식은 템플릿 매개 변수 **CharType**과 동일한 의미입니다.

## <a name="close"></a>  messages::close

메시지 카탈로그를 닫습니다.

```cpp
void close(catalog _Catval) const;
```

### <a name="parameters"></a>매개 변수

*_Catval* \
닫을 카탈로그입니다.

### <a name="remarks"></a>주의

멤버 함수는 [do_close](#do_close)(_ *Catval*)을 호출합니다.

## <a name="do_close"></a>  messages::do_close

메시지 카탈로그를 닫기 위해 호출하는 가상 함수입니다.

```cpp
virtual void do_close(catalog _Catval) const;
```

### <a name="parameters"></a>매개 변수

*_Catval* \
닫을 카탈로그입니다.

### <a name="remarks"></a>주의

Protected 멤버 함수는 [do_open](#do_open)에 대 한 이전 호출에 의해 열려 있어야 하는 메시지 카탈로그 *_catval*을 닫습니다.

*_Catval*은 닫히지 않은 이전에 연 카탈로그에서 가져와야 합니다.

### <a name="example"></a>예제

`do_close`를 호출하는 [close](#close)에 대한 예제를 참조하세요.

## <a name="do_get"></a>  messages::do_get

메시지 카탈로그를 검색하기 위해 호출하는 가상 함수입니다.

```cpp
virtual string_type do_get(
    catalog _Catval,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>매개 변수

*_Catval* \
검색할 메시지 카탈로그를 지정하는 ID 값입니다.

@No__t_1 ( *_s* )
메시지 카탈로그에서 메시지를 찾는 데 사용되는 첫 번째 식별자입니다.

*메시지 \ (_s)*
메시지 카탈로그에서 메시지를 찾는 데 사용되는 두 번째 식별자입니다.

*_Dfault* \
오류 시 반환할 문자열입니다.

### <a name="return-value"></a>반환 값

오류가 발생 했을 때 *_Dfault* 의 복사본을 반환 합니다. 그렇지 않으면 지정된 메시지 시퀀스의 복사본을 반환합니다.

### <a name="remarks"></a>주의

Protected 멤버 함수는 메시지 카탈로그 _Aampm에서 메시지 시퀀스를 가져오려고 시도 합니다. 이 작업을 수행 하는 동안에는 *_* , *_Message*및 *_lfault* 를 사용할 수 있습니다.

### <a name="example"></a>예제

`do_get`을 호출하는 [get](#get)에 대한 예제를 참조하세요.

## <a name="do_open"></a>  messages::do_open

메시지 카탈로그를 열기 위해 호출하는 가상 함수입니다.

```cpp
virtual catalog do_open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>매개 변수

@No__t_1 *이름 (_s)*
검색할 카탈로그의 이름입니다.

*_Loc* \
카탈로그에서 검색되는 로캘입니다.

### <a name="return-value"></a>반환 값

오류 시 0보다 작은 것으로 비교되는 값을 반환합니다. 그렇지 않으면 반환된 값은 나중에 [get](#get)을 호출할 때 첫 번째 인수로 사용할 수 있습니다.

### <a name="remarks"></a>주의

Protected 멤버 함수는 이름이 *_Catname*인 메시지 카탈로그를 열려고 시도 합니다. 이렇게 하려면 로캘 *_Loc* 를 사용할 수 있습니다.

반환 값은 나중에 [close](#close)를 호출할 때 인수로 사용해야 합니다.

### <a name="example"></a>예제

`do_open`을 호출하는 [open](#open)에 대한 예제를 참조하세요.

## <a name="get"></a>  messages::get

메시지 카탈로그를 불러옵니다.

```cpp
string_type get(
    catalog _CatVal,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```

### <a name="parameters"></a>매개 변수

*_Catval* \
검색할 메시지 카탈로그를 지정하는 ID 값입니다.

@No__t_1 ( *_s* )
메시지 카탈로그에서 메시지를 찾는 데 사용되는 첫 번째 식별자입니다.

*메시지 \ (_s)*
메시지 카탈로그에서 메시지를 찾는 데 사용되는 두 번째 식별자입니다.

*_Dfault* \
오류 시 반환할 문자열입니다.

### <a name="return-value"></a>반환 값

오류가 발생 했을 때 *_Dfault* 의 복사본을 반환 합니다. 그렇지 않으면 지정된 메시지 시퀀스의 복사본을 반환합니다.

### <a name="remarks"></a>주의

멤버 함수는 [do_get](#do_get)( `_Catval`, `_Set`, `_Message`, `_Dfault`)를 반환합니다.

## <a name="messages"></a>  messages::messages

메시지 패싯 생성자 함수입니다.

```cpp
explicit messages(
    size_t _Refs = 0);

protected: messages(
    const char* _Locname,
    size_t _Refs = 0);
```

### <a name="parameters"></a>매개 변수

*참조 (_s)* \
개체에 대한 메모리 관리 형식을 지정하는 데 사용하는 정수값입니다.

*_Locname* \
로캘 이름입니다.

### <a name="remarks"></a>주의

*_Refs* 매개 변수에 사용할 수 있는 값은 다음과 같습니다.

- 0: 개체를 포함하는 로캘에 의해 개체의 수명이 관리됩니다.

- 1: 개체의 수명을 수동으로 관리해야 합니다.

- \> 1: 이러한 값이 정의 되어 있지 않습니다.

소멸자는 보호되므로 직접적인 예제는 확인할 수 없습니다.

생성자는 **locale::** [facet](../standard-library/locale-class.md#facet_class)( `_Refs`)를 통해 해당 기준 개체를 초기화합니다.

## <a name="open"></a>  messages::open

메시지 카탈로그를 엽니다.

```cpp
catalog open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>매개 변수

@No__t_1 *이름 (_s)*
검색할 카탈로그의 이름입니다.

*_Loc* \
카탈로그에서 검색되는 로캘입니다.

### <a name="return-value"></a>반환 값

오류 시 0보다 작은 것으로 비교되는 값을 반환합니다. 그렇지 않으면 반환된 값은 나중에 [get](#get)을 호출할 때 첫 번째 인수로 사용할 수 있습니다.

### <a name="remarks"></a>주의

멤버 함수는 [do_open](#do_open)( `_Catname`, `_Loc`)를 반환합니다.

## <a name="string_type"></a>  messages::string_type

`basic_string` 형식의 문자가 포함된 `CharType` 형식의 문자열을 설명하는 형식입니다.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>주의

이 형식은 개체가 메시지 시퀀스의 복사본을 저장할 수 있는 클래스 템플릿 [basic_string](../standard-library/basic-string-class.md) 의 특수화를 설명 합니다.

## <a name="see-also"></a>참조

[\<locale>](../standard-library/locale.md)\
[messages_base 클래스](../standard-library/messages-base-class.md)\
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)

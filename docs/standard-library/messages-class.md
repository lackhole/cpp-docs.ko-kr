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
ms.openlocfilehash: 7a024a8cad8c536b25127d033468874de5ebd8af
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383583"
---
# <a name="messages-class"></a>messages 클래스

지정된 로캘에 대한 국제화된 메시지의 카탈로그에서 지역화된 메시지를 검색하기 위해 로캘 패싯으로 사용할 수 있는 개체에 대해 설명하는 템플릿 클래스입니다.

현재 메시지 클래스가 구현되는 동안 메시지가 없습니다.

## <a name="syntax"></a>구문

```cpp
template <class CharType>
class messages : public messages_base;
```

### <a name="parameters"></a>매개 변수

*CharType*<br/>
로캘의 문자를 인코딩하기 위해 프로그램 내 사용하는 형식입니다.

## <a name="remarks"></a>설명

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

### <a name="remarks"></a>설명

이 형식은 템플릿 매개 변수 **CharType**의 동의어입니다.

## <a name="close"></a>  messages::close

메시지 카탈로그를 닫습니다.

```cpp
void close(catalog _Catval) const;
```

### <a name="parameters"></a>매개 변수

*_Catval*<br/>
닫을 카탈로그입니다.

### <a name="remarks"></a>설명

멤버 함수는 [do_close](#do_close)(_ *Catval*)을 호출합니다.

## <a name="do_close"></a>  messages::do_close

메시지 카탈로그를 닫기 위해 호출하는 가상 함수입니다.

```cpp
virtual void do_close(catalog _Catval) const;
```

### <a name="parameters"></a>매개 변수

*_Catval*<br/>
닫을 카탈로그입니다.

### <a name="remarks"></a>설명

보호 된 멤버 함수는 메시지 카탈로그를 닫습니다 *_Catval*에 열려 있어야 이전 호출에 의해 [do_open](#do_open)합니다.

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

*_Catval*<br/>
검색할 메시지 카탈로그를 지정하는 ID 값입니다.

*_Set*<br/>
메시지 카탈로그에서 메시지를 찾는 데 사용되는 첫 번째 식별자입니다.

*_Message*<br/>
메시지 카탈로그에서 메시지를 찾는 데 사용되는 두 번째 식별자입니다.

*_Dfault*<br/>
오류 시 반환할 문자열입니다.

### <a name="return-value"></a>반환 값

복사본을 반환 *_Dfault* 실패 합니다. 그렇지 않으면 지정된 메시지 시퀀스의 복사본을 반환합니다.

### <a name="remarks"></a>설명

보호 된 멤버 함수는 메시지 카탈로그에서 메시지 시퀀스를 가져오려고 시도 *_Catval*합니다. 만들 수 있습니다 사용 *설정 (_s)* 를 *(_m)*, 및 *_Dfault* 그렇게 합니다.

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

*_Catname*<br/>
검색할 카탈로그의 이름입니다.

*_Loc*<br/>
카탈로그에서 검색되는 로캘입니다.

### <a name="return-value"></a>반환 값

오류 시 0보다 작은 것으로 비교되는 값을 반환합니다. 그렇지 않으면 반환된 값은 나중에 [get](#get)을 호출할 때 첫 번째 인수로 사용할 수 있습니다.

### <a name="remarks"></a>설명

보호 된 멤버 함수는 이름이 메시지 카탈로그를 열려고 *_Catname*합니다. 만들 수 있습니다 로캘을 사용할 *_Loc* 이렇게

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

*_Catval*<br/>
검색할 메시지 카탈로그를 지정하는 ID 값입니다.

*_Set*<br/>
메시지 카탈로그에서 메시지를 찾는 데 사용되는 첫 번째 식별자입니다.

*_Message*<br/>
메시지 카탈로그에서 메시지를 찾는 데 사용되는 두 번째 식별자입니다.

*_Dfault*<br/>
오류 시 반환할 문자열입니다.

### <a name="return-value"></a>반환 값

복사본을 반환 *_Dfault* 실패 합니다. 그렇지 않으면 지정된 메시지 시퀀스의 복사본을 반환합니다.

### <a name="remarks"></a>설명

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

*_Refs*<br/>
개체에 대한 메모리 관리 형식을 지정하는 데 사용하는 정수값입니다.

*_Locname*<br/>
로캘 이름입니다.

### <a name="remarks"></a>설명

에 대 한 가능한 값을 *_Refs* 매개 변수 및 중요성은:

- 0: 개체의 수명은 포함 하는 로캘에 의해 관리 됩니다.

- 1: 개체의 수명은 수동으로 관리 해야 합니다.

- \> 1: 이러한 값이 정의 되지 않습니다.

소멸자는 보호되므로 직접적인 예제는 확인할 수 없습니다.

생성자는 **locale::**[facet](../standard-library/locale-class.md#facet_class)( `_Refs`)를 통해 해당 기본 개체를 초기화합니다.

## <a name="open"></a>  messages::open

메시지 카탈로그를 엽니다.

```cpp
catalog open(
    const string& _Catname,
    const locale& _Loc) const;
```

### <a name="parameters"></a>매개 변수

*_Catname*<br/>
검색할 카탈로그의 이름입니다.

*_Loc*<br/>
카탈로그에서 검색되는 로캘입니다.

### <a name="return-value"></a>반환 값

오류 시 0보다 작은 것으로 비교되는 값을 반환합니다. 그렇지 않으면 반환된 값은 나중에 [get](#get)을 호출할 때 첫 번째 인수로 사용할 수 있습니다.

### <a name="remarks"></a>설명

멤버 함수는 [do_open](#do_open)( `_Catname`, `_Loc`)를 반환합니다.

## <a name="string_type"></a>  messages::string_type

`basic_string` 형식의 문자가 포함된 `CharType` 형식의 문자열을 설명하는 형식입니다.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>설명

이 형식은 개체가 메시지 시퀀스의 복사본을 저장할 수 있는 템플릿 클래스 [basic_string](../standard-library/basic-string-class.md)의 특수화를 설명합니다.

## <a name="see-also"></a>참고자료

[\<locale>](../standard-library/locale.md)<br/>
[messages_base 클래스](../standard-library/messages-base-class.md)<br/>
[C++ 표준 라이브러리의 스레드 보안](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>

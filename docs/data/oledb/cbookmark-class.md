---
title: CBookmark 클래스
ms.date: 11/04/2016
f1_keywords:
- ATL.CBookmark
- ATL::CBookmark<nSize>
- CBookmark
- ATL.CBookmark<nSize>
- ATL::CBookmark
- CBookmark<0>.CBookmark<0>
- CBookmark::CBookmark
- ATL.CBookmark.CBookmark
- CBookmark.CBookmark
- CBookmark
- ATL::CBookmark<0>::CBookmark<0>
- ATL.CBookmark<0>.CBookmark<0>
- CBookmark<0>::CBookmark<0>
- ATL::CBookmark::CBookmark
- ATL.CBookmark<0>.GetBuffer
- ATL.CBookmark.GetBuffer
- ATL::CBookmark<0>::GetBuffer
- ATL::CBookmark::GetBuffer
- CBookmark.GetBuffer
- ATL::CBookmark<nSize>::GetBuffer
- ATL.CBookmark<nSize>.GetBuffer
- CBookmark<0>.GetBuffer
- CBookmark<nSize>::GetBuffer
- CBookmark<0>::GetBuffer
- CBookmark<nSize>.GetBuffer
- CBookmark::GetBuffer
- CBookmark::GetSize
- ATL.CBookmark<nSize>.GetSize
- CBookmark<nSize>.GetSize
- CBookmark.GetSize
- ATL::CBookmark::GetSize
- CBookmark<0>::GetSize
- ATL::CBookmark<nSize>::GetSize
- ATL.CBookmark<0>.GetSize
- ATL::CBookmark<0>::GetSize
- ATL.CBookmark.GetSize
- CBookmark<0>.GetSize
- CBookmark<nSize>::GetSize
- CBookmark<0>::SetBookmark
- ATL.CBookmark<0>.SetBookmark
- CBookmark<0>.SetBookmark
- SetBookmark
- ATL::CBookmark::SetBookmark
- ATL::CBookmark<0>::SetBookmark
- CBookmark.SetBookmark
- ATL.CBookmark.SetBookmark
- CBookmark::SetBookmark
- CBookmark<0>::operator=
- CBookmark<0>.operator=
- ATL.CBookmark.operator=
- CBookmark::operator=
- ATL.CBookmark<0>.operator=
- ATL::CBookmark<0>::operator=
- CBookmark.operator=
- ATL::CBookmark::operator=
helpviewer_keywords:
- CBookmark class
- CBookmark class, constructor
- GetBuffer method
- GetSize method
- SetBookmark method
- = operator, with OLE DB templates
- operator =, bookmarks
- operator=, bookmarks
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
ms.openlocfilehash: fb2e3ec99471405f9c6521e0b70672c1da1b755c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59030143"
---
# <a name="cbookmark-class"></a>CBookmark 클래스

버퍼에서 책갈피 값을 보유합니다.

## <a name="syntax"></a>구문

```cpp
template < DBLENGTH nSize = 0 >
class CBookmark : public CBookmarkBase

template <>
class CBookmark< 0 > : public CBookmarkBase
```

### <a name="parameters"></a>매개 변수

*nSize*<br/>
크기 (바이트)는 책갈피 버퍼입니다. 때 *nSize* 이 0 인 책갈피 버퍼 런타임에 동적으로 생성 됩니다.

## <a name="requirements"></a>요구 사항

**헤더:** atldbcli.h

## <a name="members"></a>멤버

### <a name="methods"></a>메서드

|||
|-|-|
|[CBookmark](#cbookmark)|생성자|
|[GetBuffer](#getbuffer)|버퍼에 대 한 포인터를 검색합니다.|
|[GetSize](#getsize)|바이트 버퍼의 크기를 검색합니다.|
|[SetBookmark](#setbookmark)|책갈피 값을 설정 합니다.|

### <a name="operators"></a>연산자

|||
|-|-|
|[연산자 =](#operator)|할당 `CBookmark` 다른 클래스입니다.|

## <a name="remarks"></a>설명

`CBookmark<0>` 템플릿 특수화 `CBookmark`; 해당 버퍼는 런타임 시 동적으로 생성 됩니다.

## <a name="cbookmark"></a> Cbookmark:: Cbookmark

생성자입니다.

### <a name="syntax"></a>구문

```cpp
CBookmark();
CBookmark(DBLENGTH nSize);
```

#### <a name="parameters"></a>매개 변수

*nSize*<br/>
[in] 바이트 책갈피 버퍼의 크기입니다.

### <a name="remarks"></a>설명

NULL이 고, 버퍼 크기를 0으로 버퍼를 설정 하는 첫 번째 함수입니다. 버퍼 크기를 설정 하는 두 번째 함수 *nSize*, 및의 바이트 배열 버퍼 *nSize* 바이트입니다.

> [!NOTE]
>  이 함수는 사용할 수 있습니다만 `CBookmark<0>`합니다.

## <a name="getbuffer"></a> CBookmark::GetBuffer

책갈피 버퍼에 대 한 포인터를 검색합니다.

### <a name="syntax"></a>구문

```cpp
virtual BYTE* GetBuffer() const throw();
```

### <a name="return-value"></a>반환 값

책갈피 버퍼에 대 한 포인터입니다.

## <a name="getsize"></a> CBookmark::GetSize

책갈피 버퍼의 크기를 검색합니다.

### <a name="syntax"></a>구문

```cpp
virtual DBLENGTH GetSize() const throw();
```

### <a name="return-value"></a>반환 값

버퍼의 크기(바이트)입니다.

## <a name="setbookmark"></a> Cbookmark:: Setbookmark

참조 하는 책갈피 값을 복사 *pBuffer* 에 `CBookmark` 버퍼링 및 버퍼 크기를 설정 하 *nSize*합니다.

### <a name="syntax"></a>구문

```cpp
HRESULT SetBookmark(DBLENGTH nSize, BYTE* pBuffer) throw();
```

#### <a name="parameters"></a>매개 변수

*nSize*<br/>
[in] 책갈피 버퍼의 크기입니다.

*pBuffer*<br/>
[in] 책갈피 값이 들어 있는 바이트 배열에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT입니다.

### <a name="remarks"></a>설명

이 함수는 사용할 수 있습니다만 `CBookmark<0>`합니다.

## <a name="operator"></a> Cbookmark:: Operator =

할당 된 `CBookmark` 다른 개체입니다.

### <a name="syntax"></a>구문

```cpp
CBookmark& operator =(const CBookmark& bookmark) throw();
```

### <a name="remarks"></a>설명

이 연산자에만 필요한 `CBookmark<0>`합니다.

## <a name="see-also"></a>참고자료

[OLE DB 소비자 템플릿](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 소비자 템플릿 참조](../../data/oledb/ole-db-consumer-templates-reference.md)
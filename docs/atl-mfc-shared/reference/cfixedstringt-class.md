---
title: CFixedStringT 클래스
ms.date: 03/27/2019
f1_keywords:
- CFixedStringT
- CSTRINGT/ATL::CFixedStringT
- CSTRINGT/ATL::CFixedStringT::CFixedStringT
helpviewer_keywords:
- CFixedStringT class
- shared classes, CFixedStringT
ms.assetid: 6d4171ba-3104-493a-a6cc-d515f4ba9a4b
ms.openlocfilehash: 6c7649b7131e3b1620112acf89867d0731d7265d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62235167"
---
# <a name="cfixedstringt-class"></a>CFixedStringT 클래스

이 클래스는 고정된 문자 버퍼를 사용 하 여 문자열 개체를 나타냅니다.

## <a name="syntax"></a>구문

```
template<class StringType, int t_nChars>
class CFixedStringT : private CFixedStringMgr, public StringType
```

#### <a name="parameters"></a>매개 변수

*StringType*<br/>
고정된 문자열 개체에 대 한 기본 클래스로 사용 될 수 있습니다 및 `CStringT`-기반 형식입니다. 몇 가지 예로 `CString`, `CStringA`, 및 `CStringW`합니다.

*t_nChars*<br/>
버퍼에 저장 되는 문자의 수입니다.

## <a name="members"></a>멤버

### <a name="public-constructors"></a>Public 생성자

|이름|설명|
|----------|-----------------|
|[CFixedStringT::CFixedStringT](#cfixedstringt)|문자열 개체에 대 한 생성자입니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CFixedStringT::operator =](#operator_eq)|새 값을 할당 한 `CFixedStringT` 개체입니다.|

## <a name="remarks"></a>설명

이 클래스에 따라 사용자 지정 문자열 클래스의 예로 `CStringT`합니다. 비슷하지만 두 클래스 구현에서 다릅니다. 간의 주요 차이점은 `CFixedStringT` 고 `CStringT` 됩니다.

- 첫 문자의 버퍼 개체의 일부로 할당 되 고 크기가 *t_nChars*합니다. 따라서는 `CFixedString` 성능 향상을 위해 인접 한 메모리 청크를 차지 하는 개체입니다. 그러나 경우의 콘텐츠를 `CFixedStringT` 개체 크기가 다음을 초과 *t_nChars*, 버퍼를 동적으로 할당 됩니다.

- 문자 버퍼를 `CFixedStringT` 개체는 항상 동일한 길이 ( *t_nChars*). 버퍼 크기에 제한이 없는 `CStringT` 개체입니다.

- Memory manager에 대 한 `CFixedStringT` 공유할 수 있도록 사용자 지정 된을 [CStringData](../../atl-mfc-shared/reference/cstringdata-class.md) 간에 두 개 이상의 개체 `CFixedStringT` 개체 허용 되지 않습니다. `CStringT` 개체에는 이러한 제한이 없습니다.

사용자 지정에 대 한 자세한 내용은 `CFixedStringT` 문자열 개체에 대 한 메모리 관리 일반적으로 살펴보고 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`IAtlStringMgr`

`StringType`

`CFixedStringMgr`

`CFixedStringT`

## <a name="requirements"></a>요구 사항

**헤더:** cstringt.h

##  <a name="cfixedstringt"></a>  CFixedStringT::CFixedStringT

`CFixedStringT` 개체를 생성합니다.

```
CFixedStringT() throw();
explicit CFixedStringT(IAtlStringMgr* pStringMgr) throw();
CFixedStringT(const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT(const StringType& strSrc);
CFixedStringT(const StringType::XCHAR* pszSrc);
explicit CFixedStringT(const StringType::YCHAR* pszSrc);
explicit CFixedStringT(const unsigned char* pszSrc);
```

### <a name="parameters"></a>매개 변수

*pszSrc*<br/>
복사할이 null로 끝나는 문자열을 `CFixedStringT` 개체입니다.

*strSrc*<br/>
기존 `CFixedStringT` 에이 복사 될 개체 `CFixedStringT` 개체입니다.

*pStringMgr*<br/>
메모리 관리자에 대 한 포인터를 `CFixedStringT` 개체입니다. 에 대 한 자세한 `IAtlStringMgr` 및 메모리 관리에 대 한 `CFixedStringT`를 참조 하십시오 [메모리 관리 및 CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)합니다.

### <a name="remarks"></a>설명

알고 있어야 생성자에 할당 된 새 저장소를 입력된 데이터를 복사 하기 때문에 메모리 예외가 발생할 수 있습니다. 이러한 생성자 중 일부 변환 함수로 작동합니다.

##  <a name="operator_eq"></a>  CFixedStringT::operator =

기존 다시 초기화 `CFixedStringT` 새 데이터를 사용 하 여 개체입니다.

```
CFixedStringT<StringType, t_nChars>& operator=(
    const CFixedStringT<StringType, t_nChars>& strSrc);
CFixedStringT<StringType, t_nChars>& operator=(const char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const wchar_t* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const unsigned char* pszSrc);
CFixedStringT<StringType, t_nChars>& operator=(const StringType& strSrc);
```

### <a name="parameters"></a>매개 변수

*pszSrc*<br/>
복사할이 null로 끝나는 문자열을 `CFixedStringT` 개체입니다.

*strSrc*<br/>
기존 `CFixedStringT` 복사할이 `CFixedStringT` 개체입니다.

### <a name="remarks"></a>설명

알아야 할 메모리 할당 연산자를 사용 하 여 결과 보유할 새 저장소 할당 종종 되므로 때마다 예외가 발생할 수 있습니다 `CFixedStringT` 개체입니다.

## <a name="see-also"></a>참고자료

[CStringT 클래스](../../atl-mfc-shared/reference/cstringt-class.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC 공유 클래스](../../atl-mfc-shared/atl-mfc-shared-classes.md)

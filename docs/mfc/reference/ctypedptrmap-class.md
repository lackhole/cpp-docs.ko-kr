---
title: CTypedPtrMap 클래스
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrMap
- AFXTEMPL/CTypedPtrMap
- AFXTEMPL/CTypedPtrMap::GetNextAssoc
- AFXTEMPL/CTypedPtrMap::Lookup
- AFXTEMPL/CTypedPtrMap::RemoveKey
- AFXTEMPL/CTypedPtrMap::SetAt
helpviewer_keywords:
- CTypedPtrMap [MFC], GetNextAssoc
- CTypedPtrMap [MFC], Lookup
- CTypedPtrMap [MFC], RemoveKey
- CTypedPtrMap [MFC], SetAt
ms.assetid: 9f377385-c6e9-4471-8b40-8fe220c50164
ms.openlocfilehash: bc164125f867cf3e2f27b74e69b826cbed31ff1d
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58781798"
---
# <a name="ctypedptrmap-class"></a>CTypedPtrMap 클래스

`CMapPtrToPtr`, `CMapPtrToWord`, `CMapWordToPtr`및 `CMapStringToPtr`포인터-맵 클래스 개체에 대해 형식 안전 "래퍼"를 제공합니다.

## <a name="syntax"></a>구문

```
template<class BASE_CLASS, class KEY, class VALUE>
class CTypedPtrMap : public BASE_CLASS
```

#### <a name="parameters"></a>매개 변수

*BASE_CLASS*<br/>
형식화 된 포인터 맵 클래스의 기본 클래스 포인터 맵 클래스 여야 합니다 ( `CMapPtrToPtr`, `CMapPtrToWord`를 `CMapWordToPtr`, 또는 `CMapStringToPtr`).

*KEY*<br/>
지도 키로 사용 되는 개체의 클래스입니다.

*VALUE*<br/>
Map에 저장 된 개체의 클래스입니다.

## <a name="members"></a>멤버

### <a name="public-methods"></a>Public 메서드

|이름|설명|
|----------|-----------------|
|[CTypedPtrMap::GetNextAssoc](#getnextassoc)|반복에 대 한 다음 요소를 가져옵니다.|
|[CTypedPtrMap::Lookup](#lookup)|반환 된 `KEY` 기반를 `VALUE`합니다.|
|[CTypedPtrMap::RemoveKey](#removekey)|키로 지정 된 요소를 제거 합니다.|
|[CTypedPtrMap::SetAt](#setat)|맵에; 요소를 삽입합니다. 일치 하는 키가 있을 경우 기존 요소를 바꿉니다.|

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CTypedPtrMap::operator \[ \]](#operator_at)|Map에 요소를 삽입합니다.|

## <a name="remarks"></a>설명

사용 하는 경우 `CTypedPtrMap`, C++ 형식 검사 기능에 일치 하지 않는 포인터 형식으로 인 한 오류를 제거 하는 데 도움이 됩니다.

때문에 모든 `CTypedPtrMap` 함수는 인라인,이 템플릿을 사용 하 여 크게 영향을 주지 않습니다 크기 또는 코드의 속도.

사용 하 여 대 한 자세한 내용은 `CTypedPtrMap`, 문서를 참조 하세요 [컬렉션](../../mfc/collections.md) 하 고 [템플릿 기반 클래스](../../mfc/template-based-classes.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

`BASE_CLASS`

`CTypedPtrMap`

## <a name="requirements"></a>요구 사항

**헤더:** afxtempl.h

##  <a name="getnextassoc"></a>  CTypedPtrMap::GetNextAssoc

있는 지도 요소를 검색 `rNextPosition`, 다음 업데이트 `rNextPosition` 다음 지도 요소를 가리킵니다.

```
void GetNextAssoc(
    POSITION& rPosition,
    KEY& rKey,
    VALUE& rValue) const;
```

### <a name="parameters"></a>매개 변수

*rPosition*<br/>
이전 반환한 위치 값에 대 한 참조를 지정 `GetNextAssoc` 나 `BASE_CLASS` **:: GetStartPosition** 호출 합니다.

*KEY*<br/>
템플릿 매개 변수 맵의 키의 형식을 지정 합니다.

*rKey*<br/>
검색 된 요소는 반환 된 키를 지정합니다.

*VALUE*<br/>
템플릿 매개 변수 맵의 값의 형식을 지정 합니다.

*rValue*<br/>
검색된 된 요소 반환 된 값을 지정합니다.

### <a name="remarks"></a>설명

이 함수는 map의 모든 요소를 반복 하는 데 가장 유용 합니다. 않음을 유의 위치 순서 반드시 키 값 시퀀스와 동일 합니다.

검색 된 요소가 있으면 맵의 마지막으로 다음의 새 값 `rNextPosition` NULL로 설정 됩니다.

이 인라인 함수 호출 `BASE_CLASS` **:: GetNextAssoc**합니다.

##  <a name="lookup"></a>  CTypedPtrMap::Lookup

`Lookup` 해시 알고리즘을를 사용 하 여 신속 하 게 정확 하 게 일치 하는 키를 사용 하 여 지도 요소를 찾습니다.

```
BOOL Lookup(BASE_CLASS ::BASE_ARG_KEY key, VALUE& rValue) const;
```

### <a name="parameters"></a>매개 변수

*BASE_CLASS*<br/>
템플릿 매개 변수를이 map 클래스의 기본 클래스를 지정 합니다.

*key*<br/>
키 조회 요소입니다.

*VALUE*<br/>
템플릿 매개 변수를이 맵에 저장 된 값의 형식을 지정 합니다.

*rValue*<br/>
검색된 된 요소 반환 된 값을 지정합니다.

### <a name="return-value"></a>반환 값

0이 아닌 요소를 찾을 수 있습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

이 인라인 함수 호출 `BASE_CLASS` **:: Lookup**합니다.

##  <a name="operator_at"></a>  CTypedPtrMap::operator [ ]

이 연산자 좌 변의 대입문 (l-value) 에서만 사용할 수 있습니다.

```
VALUE& operator[ ](base_class ::base_arg_key key);
```

### <a name="parameters"></a>매개 변수

*VALUE*<br/>
템플릿 매개 변수를이 맵에 저장 된 값의 형식을 지정 합니다.

*BASE_CLASS*<br/>
템플릿 매개 변수를이 map 클래스의 기본 클래스를 지정 합니다.

*key*<br/>
키 조회 하거나 지도에 만들 요소입니다.

### <a name="remarks"></a>설명

지정된 된 키를 사용 하 여 지도 요소가 이면 새 요소가 만들어집니다. 경우 없음 "오른쪽" (r-value)이이 연산자에 해당 맵의 키를 찾을 수 없습니다 가능성이 있기 때문에 사용 된 `Lookup` 요소 검색에 대 한 멤버 함수입니다.

##  <a name="removekey"></a>  CTypedPtrMap::RemoveKey

이 멤버 함수 호출 `BASE_CLASS` **:: RemoveKey**합니다.

```
BOOL RemoveKey(KEY key);
```

### <a name="parameters"></a>매개 변수

*KEY*<br/>
템플릿 매개 변수 맵의 키의 형식을 지정 합니다.

*key*<br/>
제거할 요소의 키입니다.

### <a name="return-value"></a>반환 값

0이 아닌 항목을 찾아 제거 했습니다. 그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

설명, 자세한 [CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)합니다.

##  <a name="setat"></a>  CTypedPtrMap::SetAt

이 멤버 함수 호출 `BASE_CLASS` **:: SetAt**합니다.

```
void SetAt(KEY key, VALUE newValue);
```

### <a name="parameters"></a>매개 변수

*KEY*<br/>
템플릿 매개 변수 맵의 키의 형식을 지정 합니다.

*key*<br/>
새 값의 키 값을 지정합니다.

*newValue*<br/>
새 요소의 값은 개체 포인터를 지정 합니다.

### <a name="remarks"></a>설명

설명, 자세한 [CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)합니다.

## <a name="see-also"></a>참고자료

[MFC 샘플 수집](../../overview/visual-cpp-samples.md)<br/>
[계층 구조 차트](../../mfc/hierarchy-chart.md)<br/>
[CMapPtrToPtr 클래스](../../mfc/reference/cmapptrtoptr-class.md)<br/>
[CMapPtrToWord 클래스](../../mfc/reference/cmapptrtoword-class.md)<br/>
[CMapWordToPtr 클래스](../../mfc/reference/cmapwordtoptr-class.md)<br/>
[CMapStringToPtr 클래스](../../mfc/reference/cmapstringtoptr-class.md)

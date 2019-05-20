---
title: 컬렉션 클래스 도우미
ms.date: 11/04/2016
helpviewer_keywords:
- DestructElements function
- ConstructElements function
- SerializeElements function
- collection classes [MFC], helper functions
- helper functions collection class [MFC]
ms.assetid: bc3a2368-9edd-4748-9e6a-13cba79517ca
ms.openlocfilehash: 6839427d916068deaf2041dd21a282e0b470f404
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/14/2019
ms.locfileid: "65612266"
---
# <a name="collection-class-helpers"></a>컬렉션 클래스 도우미

컬렉션 클래스 `CMap`, `CList`, 및 `CArray` 비교, 복사 및 요소를 직렬화 하는 작업으로 이러한 목적에 대 한 전역 템플릿 기반 도우미 함수를 사용 합니다. 기반으로 클래스 구현의 일부로 `CMap`, `CList`, 및 `CArray`, 맵, 목록 또는 배열에 저장 된 데이터의 형식에 맞게 조정 된 버전을 사용 하 여 필요에 따라 이러한 함수를 재정의 해야 합니다. 와 같은 도우미 함수를 재정의 하는 방법은 `SerializeElements`, 문서를 참조 [컬렉션: 형식이 안전한 컬렉션을 만드는 방법](../../mfc/how-to-make-a-type-safe-collection.md)합니다. 사실은 `ConstructElements` 고 `DestructElements` 사용 되지 않습니다.

Microsoft Foundation Class 라이브러리는 afxtempl.h 컬렉션 클래스를 사용자 지정 하는 데에 다음 전역 함수를 제공 합니다.

### <a name="collection-class-helpers"></a>컬렉션 클래스 도우미

|||
|-|-|
|[CompareElements](#compareelements)|요소가 같은지 여부를 나타냅니다.|
|[CopyElements](#copyelements)|다른 배열에서 요소를 복사 합니다.|
|[DumpElements](#dumpelements)|스트림 지향 진단 출력을 제공합니다.|
|[HashKey](#hashkey)|해시 키를 계산합니다.|
|[SerializeElements](#serializeelements)|저장 하거나 보관 파일에서 구성 요소를 검색 합니다.|

##  <a name="compareelements"></a>  CompareElements

직접 호출 [CList::Find] (clist class.md #not_found.md #clist__find 및 간접적으로 [cmap__lookup](cmap-class.md#lookup) 하 고 [cmap__operator &#91; &#93; ](cmap-class.md#operator_at).

```
template<class TYPE, class ARG_TYPE>
BOOL AFXAPI
CompareElements(
    const TYPE* pElement1,
    const ARG_TYPE* pElement2);
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
비교할 첫 번째 요소의 형식입니다.

*pElement1*<br/>
비교할 첫 번째 요소에 대 한 포인터입니다.

*ARG_TYPE*<br/>
비교할 두 번째 요소의 형식입니다.

*pElement2*<br/>
비교할 두 번째 요소에 대 한 포인터입니다.

### <a name="return-value"></a>반환 값

개체에서 가리키는 경우 0이 아닌 *pElement1* 이 가리키는 개체와 같은지 *pElement2*그렇지 않으면 0입니다.

### <a name="remarks"></a>설명

`CMap` 사용 하 여 호출 합니다 `CMap` 템플릿 매개 변수 *키* 하 고 *ARG_KEY*합니다.

비교의 결과 반환 하는 기본 구현은  *\*pElement1* 하 고  *\*pElement2*합니다. 응용 프로그램에 적절 한 방식으로 요소를 비교 하는이 함수를 재정의 합니다.

C++ 비교 연산자를 정의 하는 언어 ( `==`) 단순 형식 (**char**, **int**, **float**등) 되지만 비교를 정의 하지 않습니다 클래스 및 구조에 대 한 연산자입니다. 사용 하려는 경우 `CompareElements` 사용 하는 컬렉션 클래스 중 하나를 인스턴스화할 때 비교 연산자를 정의 하거나 오버 로드 또는 `CompareElements` 적절 한 값을 반환 하는 버전으로 합니다.

### <a name="requirements"></a>요구 사항

   **헤더:** afxtempl.h

##  <a name="copyelements"></a>  CopyElements

이 함수에서 직접 호출 됩니다 [CArray::Append](carray-class.md#append) 하 고 [CArray::Copy](carray-class.md#copy)합니다.

```
template<class TYPE>
void AFXAPI CopyElements(
    TYPE* pDest,
    const TYPE* pSrc,
    INT_PTR nCount);
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
복사할 요소의 형식을 지정 하는 템플릿 매개 변수

*pDest*<br/>
요소를 복사할 대상에 대 한 포인터입니다.

*pSrc*<br/>
복사할 요소의 원본에 대 한 포인터입니다.

*nCount*<br/>
복사할 요소의 수입니다.

### <a name="remarks"></a>설명

단순 할당 연산자를 사용 하 여 기본 구현 ( **=** ) 복사 작업을 수행 합니다. 복사할 형식에 오버 로드 된 연산자가 없는 경우 =를 기본 구현에서는 비트 복사를 수행 합니다.

이 및 다른 도우미 함수를 구현에 대 한 자세한 내용은 문서를 참조 하세요. [컬렉션: 형식이 안전한 컬렉션을 만드는 방법](../how-to-make-a-type-safe-collection.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxtempl.h

##  <a name="dumpelements"></a>  DumpElements

재정의 된 경우 컬렉션의 요소에 대 한 텍스트 형태로 스트림 지향 진단 출력을 제공 합니다.

```
template<class TYPE>
void  AFXAPI DumpElements(
    CDumpContext& dc,
    const TYPE* pElements,
    INT_PTR nCount);
```

### <a name="parameters"></a>매개 변수

*dc*<br/>
요소를 덤프 하는 것에 대 한 컨텍스트를 덤프 합니다.

*TYPE*<br/>
요소의 형식을 지정 하는 템플릿 매개 변수

*pElements*<br/>
요소를 덤프할 수에 대 한 포인터입니다.

*nCount*<br/>
덤프할 수 있는 요소의 수입니다.

### <a name="remarks"></a>설명

합니다 `CArray::Dump`, `CList::Dump`, 및 `CMap::Dump` 덤프의 깊이 0 보다 큰 경우이 함수 호출 합니다.

기본 구현은 아무 작업도 수행하지 않습니다. 컬렉션의 요소에서 파생 된 경우 `CObject`를 재정의 일반적으로 컬렉션의 요소를 반복 호출 `Dump` 의 각 요소에 대 한 합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxtempl.h

##  <a name="hashkey"></a>  HashKey

지정된 된 키에 대 한 해시 값을 계산합니다.

```
template<class ARG_KEY>
AFX_INLINE UINT AFXAPI HashKey(ARG_KEY  key);
```

### <a name="parameters"></a>매개 변수

*ARG_KEY*<br/>
템플릿 매개 변수를 맵 키에 액세스 하는 데 데이터 형식을 지정 합니다.

*key*<br/>
해시 값 계산 해야 하는 키입니다.

### <a name="return-value"></a>반환 값

키의 해시 값입니다.

### <a name="remarks"></a>설명

이 함수에서 직접 호출 됩니다 [CMap::RemoveKey](cmap-class.md#removekey) 및 간접적 [CMap::Lookup](cmap-class.md#lookup) 하 고 [CMap::Operator &#91; &#93; ](cmap-class.md#operator_at).

기본 구현은 이동 하 여 해시 값을 만듭니다 *키* 네 가지 위치에서 오른쪽입니다. 응용 프로그램에 대 한 적절 한 해시 값을 반환할 수 있도록이 함수를 재정의 합니다.

### <a name="example"></a>예제

```cpp
template <> UINT AFXAPI HashKey(unsigned __int64 key)
{
   // Generate the hash value by XORing the lower 32 bits of the number
   // with the upper 32 bits
   return(UINT(key) ^ UINT(key >> 32));
}
```

### <a name="requirements"></a>요구 사항

  **헤더** afxtempl.h

##  <a name="serializeelements"></a>  SerializeElements

[CArray](carray-class.md)하십시오 [CList](clist-class.md), 및 [CMap](cmap-class.md) 요소를 serialize 할이 함수를 호출 합니다.

```
template<class TYPE>
void AFXAPI SerializeElements(CArchive& ar, TYPE* pElements, INT_PTR nCount);
```

### <a name="parameters"></a>매개 변수

*TYPE*<br/>
요소의 형식을 지정 하는 템플릿 매개 변수

*ar*<br/>
보관 개체를 보관 하는입니다.

*pElements*<br/>
보관 되 고 요소에 대 한 포인터입니다.

*nCount*<br/>
보관 되는 요소의 수

### <a name="remarks"></a>설명

기본 구현에서는 비트 읽기 또는 쓰기입니다.

이 및 다른 도우미 함수를 구현에 대 한 자세한 내용은 문서를 참조 하세요. [컬렉션: 형식이 안전한 컬렉션을 만드는 방법](../how-to-make-a-type-safe-collection.md)합니다.

### <a name="example"></a>예제

문서에서 예제를 참조 하세요 [컬렉션: 형식이 안전한 컬렉션을 만드는 방법](../how-to-make-a-type-safe-collection.md)합니다.

### <a name="requirements"></a>요구 사항

  **헤더** afxtempl.h

## <a name="see-also"></a>참고자료

[매크로 및 전역](mfc-macros-and-globals.md)<br/>
[CMap 클래스](cmap-class.md)<br/>
[CList 클래스](clist-class.md)<br/>
[CArray 클래스](carray-class.md)

---
title: 마샬링 전역 함수
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
ms.openlocfilehash: cac6e316ad6b5d3f49c171c940d9129060744aee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62274696"
---
# <a name="marshaling-global-functions"></a>마샬링 전역 함수

이러한 함수를 사용 하면 마샬링 및 마샬링 데이터 인터페이스 포인터를 변환에 대 한 지원.

> [!IMPORTANT]
>  다음 표에 나열 된 함수를 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

|||
|-|-|
|[AtlFreeMarshalStream](#atlfreemarshalstream)|마샬링 데이터를 해제 및 `IStream` 포인터입니다.|
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|새 스트림 개체를 만들고 지정 된 인터페이스 포인터를 마샬링합니다.|
|[AtlUnmarshalPtr](#atlunmarshalptr)|에 대 한 인터페이스 포인터를 스트림의 마샬링 데이터를 변환합니다.|

## <a name="requirements"></a>요구 사항:

**헤더:** atlbase.h

##  <a name="atlfreemarshalstream"></a>  AtlFreeMarshalStream

스트림에서 마샬링 데이터를 해제한 다음 스트림 포인터를 해제합니다.

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
[in] 에 대 한 포인터를 `IStream` 마샬링하는 데 사용 하는 스트림 인터페이스입니다.

### <a name="example"></a>예제

예를 참조 하세요 [AtlMarshalPtrInProc](#atlmarshalptrinproc)합니다.

##  <a name="atlmarshalptrinproc"></a>  AtlMarshalPtrInProc

새 스트림 개체를 만들고, 프록시의 CLSID를 스트림에 쓰고, 프록시를 스트림으로 초기화하는 데 필요한 데이터를 작성하여 제공된 인터페이스 포인터를 마샬링합니다.

```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```

### <a name="parameters"></a>매개 변수

*pUnk*<br/>
[in] 마샬링될 인터페이스에 대 한 포인터입니다.

*iid*<br/>
[in] 마샬링되 인터페이스의 GUID입니다.

*ppStream*<br/>
[out] 에 대 한 포인터를 `IStream` 마샬링에 사용 되는 새 스트림 개체의 인터페이스입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="remarks"></a>설명

MSHLFLAGS_TABLESTRONG 플래그가 설정 되어 있으므로 여러 스트림 포인터를 마샬링할 수 있습니다. 포인터도 수 마샬링된 여러 번입니다.

실패 하면 마샬링 스트림 포인터를 해제 됩니다.

`AtlMarshalPtrInProc` in process 개체에 대 한 포인터에만 사용할 수 있습니다.

### <a name="example"></a>예제

[!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]

##  <a name="atlunmarshalptr"></a>  AtlUnmarshalPtr

스트림의 마샬링 데이터를 클라이언트에서 사용할 수 있는 인터페이스 포인터로 변환합니다.

```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```

### <a name="parameters"></a>매개 변수

*pStream*<br/>
[in] 역마샬링 중인 스트림에 대 한 포인터입니다.

*iid*<br/>
[in] 역마샬링 중인 인터페이스의 GUID입니다.

*ppUnk*<br/>
[out] 역마샬링 된 인터페이스 포인터입니다.

### <a name="return-value"></a>반환 값

표준 HRESULT 값입니다.

### <a name="example"></a>예제

예를 참조 하세요 [AtlMarshalPtrInProc](#atlmarshalptrinproc)합니다.

## <a name="see-also"></a>참고자료

[함수](../../atl/reference/atl-functions.md)

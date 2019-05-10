---
title: CAtlFileMapping 클래스
ms.date: 11/04/2016
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
helpviewer_keywords:
- CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
ms.openlocfilehash: d0a47a6cf0cc86409ceb9ef40d6fc6d738c86aa9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247174"
---
# <a name="catlfilemapping-class"></a>CAtlFileMapping 클래스

이 클래스의 메서드에 캐스트 연산자를 추가, 메모리 매핑된 파일을 나타냅니다 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)합니다.

> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.

## <a name="syntax"></a>구문

```
template <typename T = char>
class CAtlFileMapping : public CAtlFileMappingBase
```

#### <a name="parameters"></a>매개 변수

*T*<br/>
캐스트 연산자에 사용 되는 데이터의 형식입니다.

## <a name="members"></a>멤버

### <a name="public-operators"></a>Public 연산자

|이름|설명|
|----------|-----------------|
|[CAtlFileMapping::operator T *](#operator_t_star)|암시적인 변환이 가능 `CAtlFileMapping` 개체를 `T*`입니다.|

## <a name="remarks"></a>설명

이 클래스는 암시적으로 변환할 수 있도록 단일 캐스트 연산자를 추가 `CAtlFileMapping` 개체를 `T*`입니다. 기본 클래스에서 제공 하는 다른 멤버 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)합니다.

## <a name="inheritance-hierarchy"></a>상속 계층 구조

[CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)

`CAtlFileMapping`

## <a name="requirements"></a>요구 사항

**헤더:** atlfile.h

##  <a name="operator_t_star"></a>  CAtlFileMapping::operator T *

암시적인 변환이 가능 `CAtlFileMapping` 개체를 `T*`입니다.

```
operator T*() const throw();
```

### <a name="return-value"></a>반환 값

반환 된 `T*` 메모리 매핑된 파일의 시작 부분에 대 한 포인터입니다.

### <a name="remarks"></a>설명

호출 [CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) 로 반환된 된 포인터를 재해석 하 고는 `T*` 여기서 *T* 유형은이 클래스의 템플릿 매개 변수로 사용 합니다.

## <a name="see-also"></a>참고자료

[CAtlFileMappingBase 클래스](../../atl/reference/catlfilemappingbase-class.md)<br/>
[클래스 개요](../../atl/atl-class-overview.md)

---
title: 항목 (C++ COM 특성)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: 703a55ee7c56b64a5b168016770508508bab09e0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036304"
---
# <a name="entry"></a>entry

DLL의 진입점을 식별 하 여 모듈에는 내보낸된 함수 또는 상수를 지정 합니다.

## <a name="syntax"></a>구문

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>매개 변수

*ID*<br/>
진입점의 ID입니다.

## <a name="remarks"></a>설명

**항목** C++ 특성에 동일한 기능을 합니다 [항목](/windows/desktop/Midl/entry) MIDL 특성입니다.

## <a name="example"></a>예제

예를 참조 하세요 [idl_module](idl-module.md) 의 사용 예에 대 한 **항목**합니다.

## <a name="requirements"></a>요구 사항

### <a name="attribute-context"></a>특성 컨텍스트

|||
|-|-|
|**적용 대상**|`idl_module` 특성|
|**반복 가능**|아니요|
|**필수 특성**|없음|
|**잘못된 특성**|없음|

자세한 내용은 [특성 컨텍스트](cpp-attributes-com-net.md#contexts)를 참조하세요.

## <a name="see-also"></a>참고자료

[IDL 특성](idl-attributes.md)
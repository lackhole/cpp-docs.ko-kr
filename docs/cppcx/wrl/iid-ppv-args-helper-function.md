---
title: IID_PPV_ARGS_Helper 함수
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
ms.openlocfilehash: e7733ae6084b64c20dff5a2c35d7a31c614d6e44
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500502"
---
# <a name="iid_ppv_args_helper-function"></a>IID_PPV_ARGS_Helper 함수

지정 된 인수의 형식이 `IUnknown` 인터페이스에서 파생 되는지 확인 합니다.

> [!IMPORTANT]
> 이 템플릿 특수화는 WRL 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다. 대신 [IID_PPV_ARGS](/windows/win32/api/combaseapi/nf-combaseapi-iid_ppv_args) 를 사용 해야 합니다.

## <a name="syntax"></a>구문

```cpp
template<typename T>
void** IID_PPV_ARGS_Helper(
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp
);
```

### <a name="parameters"></a>매개 변수

*T*<br/>
인수 *pp*의 유형입니다.

*pp*<br/>
이중 간접 포인터입니다.

## <a name="return-value"></a>반환 값

인수 *pp* 를 **void**포인터로 캐스팅 합니다.

## <a name="remarks"></a>설명

템플릿 매개 변수 *T* 가에서 `IUnknown`파생 되지 않으면 컴파일 시간 오류가 발생 합니다.

## <a name="requirements"></a>요구 사항

**헤더:** client.h


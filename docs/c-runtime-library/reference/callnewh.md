---
title: _callnewh
ms.date: 11/04/2016
apiname:
- _callnewh
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _callnewh
helpviewer_keywords:
- _callnewh
ms.assetid: 4dcb73e9-6384-4d12-a973-a8807d4de7a8
ms.openlocfilehash: 98526f6c8c40b71104345563db71ef098b6cfb8d
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70739817"
---
# <a name="_callnewh"></a>_callnewh

현재 설치된 *새 처리기*를 호출합니다.

## <a name="syntax"></a>구문

```cpp
int _callnewh(
   size_t size
   )
```

### <a name="parameters"></a>매개 변수

*size*<br/>
[new 연산자](../../cpp/new-operator-cpp.md)에서 할당하려고 시도한 메모리의 양입니다.

## <a name="return-value"></a>반환 값

|값|설명|
|-----------|-----------------|
|0|실패로 새 처리기가 설치 되어 있지 않거나 새 처리기가 활성화 되어 있지 않습니다.|
|1|성공할 새 처리기가 설치 되어 있고 활성 상태입니다. 메모리 할당을 다시 시도할 수 있습니다.|

## <a name="exceptions"></a>예외

이 함수는 *새 처리기*를 찾을 수 없는 경우 [bad_alloc](../../standard-library/bad-alloc-class.md)을 throw합니다.

## <a name="remarks"></a>설명

[new 연산자](../../cpp/new-operator-cpp.md)가 메모리 할당에 실패하는 경우 *새 처리기*가 호출됩니다. 그러면 후속 할당에 성공할 수 있도록 새 처리기가 메모리를 해제하는 등의 몇 가지 적절한 작업을 시작할 수 있습니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|_callnewh|internal.h|

## <a name="see-also"></a>참고자료

[_set_new_handler](set-new-handler.md)<br/>
[_set_new_mode](set-new-mode.md)<br/>

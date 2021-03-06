---
title: _set_new_mode
ms.date: 11/04/2016
api_name:
- _set_new_mode
api_location:
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_new_mode
- _set_new_mode
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
ms.openlocfilehash: b248f1c97b1ec334b7441f33862b90473e08993f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948448"
---
# <a name="_set_new_mode"></a>_set_new_mode

**Malloc**에 대 한 새 처리기 모드를 설정 합니다.

## <a name="syntax"></a>구문

```cpp
int _set_new_mode( int newhandlermode );
```

### <a name="parameters"></a>매개 변수

*newhandlermode*<br/>
**Malloc**에 대 한 새 처리기 모드 유효한 값은 0 또는 1입니다.

## <a name="return-value"></a>반환 값

**Malloc**에 대해 설정 된 이전 처리기 모드를 반환 합니다. 반환 값이 1 이면 메모리 할당이 실패 하는 경우 이전에 새 처리기 **루틴을 호출** 했음을 나타냅니다. 반환 값이 0 이면 해당 값이 반환 되지 않았음을 나타냅니다. *Newhandlermode* 인수가 0 또는 1이 아니면-1을 반환 합니다.

## <a name="remarks"></a>설명

C++ **_set_new_mode** 함수는 [malloc](malloc.md)에 대한 새 처리기 모드를 설정합니다. 새 처리기 모드는 실패 시 **malloc** 가 [_set_new_handler](set-new-handler.md)에서 설정한 대로 새 처리기 루틴을 호출 하는지 여부를 나타냅니다. 기본적으로 **malloc** 은 메모리 할당 실패 시 새 처리기 루틴을 호출 하지 않습니다. 이 기본 동작을 재정의 하 여 **malloc** 에서 메모리 할당에 실패 한 경우 **malloc** 는 **새** 연산자가 같은 이유로 실패 했을 때와 동일한 방식으로 새 처리기 루틴을 호출 합니다. 자세한 내용은 *C++ 언어 참조*의 [new](../../cpp/new-operator-cpp.md) 및 [delete](../../cpp/delete-operator-cpp.md) 연산자를 참조하세요. 기본값을 재정의하려면 다음을

```cpp
_set_new_mode(1);
```

프로그램에서 초기에 호출하거나, Newmode.obj를 사용하여 연결합니다([링크 옵션](../../c-runtime-library/link-options.md) 참조).

이 함수는 해당 매개 변수의 유효성을 검사합니다. *Newhandlermode* 가 0 또는 1이 아닌 경우 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 합니다. 계속 해 서 실행 하도록 허용한 경우 <strong>_set_new_mode</strong> 는-1을 반환 하 고 `EINVAL`errno를로 설정 합니다.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_set_new_mode**|\<new.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[메모리 할당](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[realloc](realloc.md)<br/>
[_query_new_handler](query-new-handler.md)<br/>
[_query_new_mode](query-new-mode.md)<br/>

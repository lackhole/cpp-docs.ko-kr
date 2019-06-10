---
title: _open_osfhandle
ms.date: 05/21/2019
apiname:
- _open_osfhandle
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _open_osfhandle
- open_osfhandle
helpviewer_keywords:
- open_osfhandle function
- file handles [C++], associating
- _open_osfhandle function
ms.assetid: 30d94df4-7868-4667-a401-9eb67ecb7855
ms.openlocfilehash: 9e940844eb5e37755c10999feb294981afc8683a
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821589"
---
# <a name="openosfhandle"></a>_open_osfhandle

C 런타임 파일 설명자를 기존 운영 체제 파일 핸들을 사용 하 여 연결합니다.

## <a name="syntax"></a>구문

```cpp
int _open_osfhandle (
   intptr_t osfhandle,
   int flags
);
```

### <a name="parameters"></a>매개 변수

*osfhandle*<br/>
운영 체제 파일 핸들입니다.

*flags*<br/>
허용되는 연산의 유형입니다.

## <a name="return-value"></a>반환 값

정상적으로 실행되면 **_open_osfhandle**은 C 런타임 파일 설명자를 반환합니다. 그렇지 않은 경우 -1을 반환합니다.

## <a name="remarks"></a>설명

합니다 **_open_osfhandle** 함수를 C 런타임 파일 설명자를 할당 합니다. 지정 된 운영 체제 파일 핸들을 사용 하 여이 파일 설명자 연결 *osfhandle*합니다. 컴파일러 경고를 방지하려면 *osfhandle* 인수를 **HANDLE**에서 **intptr_t**로 캐스팅합니다. *플래그* 인수는 \<fcntl.h>에 정의된 매니페스트 상수 중 하나 이상으로 구성된 정수 식입니다. 비트 OR 연산자를 사용할 수 있습니다 ( **&#124;** ) 형식으로 두 개 이상의 매니페스트 상수를 결합 하는 *플래그* 인수입니다.

매니페스트 상수는 \<fcntl.h>에 정의되어 있습니다.

|||
|-|-|
| **\_O\_APPEND** | 모든 쓰기 작업 전에 파일 포인터를 파일 끝에 배치합니다. |
| **\_O\_RDONLY** | 읽기 전용으로 파일을 엽니다. |
| **\_O\_TEXT** | 파일을 텍스트(변환됨) 모드에서 엽니다. |
| **\_O\_WTEXT** | 파일을 유니코드(변환된 UTF-16) 모드에서 엽니다. |

**_open_osfhandle** 호출이 Win32 파일 핸들의 소유권을 파일 설명자로 전송합니다. **_open_osfhandle**을 사용하여 열린 파일을 닫으려면 [\_닫기](close.md)를 호출합니다. 기본 OS 파일 핸들도 **_close**에 대한 호출에 의해 닫힙니다. 원래 핸들에 있는 Win32 함수 **CloseHandle**을 호출하지 마세요. 파일 설명자가 소유 하는 경우는 **파일 &#42;**  스트림 다음에 대 한 호출 [fclose](fclose-fcloseall.md) 파일 설명자와 기본 핸들을 닫습니다. 이 경우 파일 설명자의 **_close** 또는 원래 핸들의 **CloseHandle**을 호출하지 마세요.

## <a name="requirements"></a>요구 사항

|루틴에서 반환된 값|필수 헤더|
|-------------|---------------------|
|**_open_osfhandle**|\<io.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="see-also"></a>참고자료

[파일 처리](../../c-runtime-library/file-handling.md)<br/>
[\_get_osfhandle](get-osfhandle.md)

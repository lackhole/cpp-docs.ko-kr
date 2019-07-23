---
title: fwrite
ms.date: 11/04/2016
apiname:
- fwrite
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
- fwrite
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
ms.openlocfilehash: f05e39390f3a2d0ad41627f6aed1aecd77b57cca
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376055"
---
# <a name="fwrite"></a>fwrite

스트림에 데이터를 씁니다.

## <a name="syntax"></a>구문

```C
size_t fwrite(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>매개 변수

*buffer*<br/>
쓸 데이터에 대한 포인터입니다.

*size*<br/>
항목 크기입니다(바이트).

*count*<br/>
쓸 항목의 최대 수입니다.

*stream*<br/>
**FILE** 구조체에 대한 포인터입니다.

## <a name="return-value"></a>반환 값

**fwrite** 는 실제로 쓰여진 전체 항목 수를 반환 합니다. 오류가 발생 하는 경우 *count* 보다 적을 수 있습니다. 또한 오류가 발생하면 파일 위치 표시기를 확인할 수 없습니다. *스트림* 또는 *버퍼가* null 포인터 이거나 쓸 홀수 바이트 수가 유니코드 모드에 지정 된 경우이 함수는 [매개 변수 유효성 검사](../../c-runtime-library/parameter-validation.md)에 설명 된 대로 잘못 된 매개 변수 처리기를 호출 합니다. 계속 해 서 실행 하도록 허용한 경우이 함수는 **errno** 를 **EINVAL** 로 설정 하 고 0을 반환 합니다.

## <a name="remarks"></a>설명

**Fwrite** 함수는 *버퍼* 에서 출력 *스트림으로*각각 *크기* 길이의 항목을 *계산* 합니다. *스트림* (있는 경우)과 연결 된 파일 포인터는 실제로 기록 된 바이트 수 만큼 증가 합니다. *스트림이* 텍스트 모드에서 열리면 각 줄 바꿈이 캐리지 리턴-줄 바꿈 쌍으로 바뀝니다. 이렇게 바뀌더라도 반환 값에는 영향을 미치지 않습니다.

*스트림이* 유니코드 변환 모드에서 열리는 경우 (예: **fopen** 을 호출 하 고 **ccs = Unicode**, **ccs = utf-16le**또는 **ccs = u t f-8**이 포함 된 모드 매개 변수를 사용 하 여 *스트림* 열기) 또는 모드가 **_setmode** 를 사용 하 여 유니코드 변환 모드를 변경 하 고 **_O_wtext**, **_o_u16text**또는 **_o_u8text**를 포함 하는 mode 매개 변수를 사용 하 여*버퍼* 를 포함 하는 **wchar_t** 의 배열에 대 한 포인터로 해석 합니다. UTF-16 데이터입니다. 이 모드에서 홀수 바이트를 쓰려고 하면 매개 변수 유효성 검사 오류가 발생합니다.

이 함수는 호출 스레드를 잠그기 때문에 스레드로부터 안전하게 보호됩니다. 잠기지 않는 버전은 **_fri_nolock**을 참조 하세요.

## <a name="requirements"></a>요구 사항

|기능|필수 헤더|
|--------------|---------------------|
|**fwrite**|\<stdio.h>|

호환성에 대한 자세한 내용은 [호환성](../../c-runtime-library/compatibility.md)을 참조하세요.

## <a name="example"></a>예제

[fread](fread.md)의 예제를 참조하세요.

## <a name="see-also"></a>참고자료

[스트림 I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_setmode](setmode.md)<br/>
[fread](fread.md)<br/>
[_fwrite_nolock](fwrite-nolock.md)<br/>
[_write](write.md)<br/>

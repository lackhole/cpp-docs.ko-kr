---
title: 파일 사용 권한 상수
ms.date: 11/04/2016
f1_keywords:
- _S_IWRITE
- _S_IREAD
helpviewer_keywords:
- S_IWRITE constant
- constants [C++], file attributes
- S_IREAD constant
- file permissions [C++]
- _S_IWRITE constant
- _S_IREAD constant
ms.assetid: 593cad33-31d1-44d2-8941-8af7d210c88c
ms.openlocfilehash: 0e042cddce6edf079aa54f114130f9750412e327
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57742709"
---
# <a name="file-permission-constants"></a>파일 사용 권한 상수

## <a name="syntax"></a>구문

```
#include <sys/stat.h>
```

## <a name="remarks"></a>주의

`_O_CREAT`(`_open`, `_sopen`)가 지정되었을 때 이러한 상수 중 하나가 필요합니다.

`pmode` 인수는 파일의 사용 권한 설정을 다음과 같이 지정합니다.

|상수|의미|
|--------------|-------------|
|`_S_IREAD`|읽기 허용|
|`_S_IWRITE`|쓰기 허용|
|`_S_IREAD` &#124; `_S_IWRITE`|읽기 및 쓰기 허용|

`pmode` 인수를 `_umask`에 대해 사용하는 경우 매니페스트 상수는 다음과 같이 권한을 설정합니다.

|상수|의미|
|--------------|-------------|
|`_S_IREAD`|쓰기가 허용되지 않음(읽기 전용)|
|`_S_IWRITE`|읽기가 허용되지 않음(쓰기 전용)|
|`_S_IREAD` &#124; `_S_IWRITE`|읽기나 쓰기 모두 허용되지 않음|

## <a name="see-also"></a>참고 항목

[_open, _wopen](../c-runtime-library/reference/open-wopen.md)<br/>
[_sopen, _wsopen](../c-runtime-library/reference/sopen-wsopen.md)<br/>
[_umask](../c-runtime-library/reference/umask.md)<br/>
[표준 형식](../c-runtime-library/standard-types.md)<br/>
[전역 상수](../c-runtime-library/global-constants.md)

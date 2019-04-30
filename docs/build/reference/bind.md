---
title: /BIND
ms.date: 11/04/2016
f1_keywords:
- /bind
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
ms.openlocfilehash: e8ba0a5f0235c8771567e4e43172bdf8c81c99a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295034"
---
# <a name="bind"></a>/BIND

```
/BIND[:PATH=path]
```

## <a name="remarks"></a>설명

이 옵션은 실행 파일 또는 DLL에 대 한 가져오기 주소 테이블에서 진입점의 주소를 설정합니다. 프로그램의 로드 시간을 줄이려면이 옵션을 사용 합니다.

프로그램 실행 파일과 Dll을 지정 합니다 *파일* EDITBIN 명령줄의 인수입니다. 선택적 *경로* /BIND 인수가 지정 된 파일을 사용 하는 Dll의 위치를 지정 합니다. 여러 디렉터리를 세미콜론으로 구분 (**;**). 하는 경우 *경로* 지정 하지 않으면 EDITBIN PATH 환경 변수에 지정 된 디렉터리를 검색 합니다. 하는 경우 *경로* 를 지정 하면 EDITBIN PATH 변수를 무시 합니다.

기본적으로 프로그램 로더 프로그램을 로드할 때 진입점의 주소를 설정 합니다. 이 프로세스는 시간의 양을 Dll의 수 및 프로그램에서 참조 하는 진입점의 수에 따라 달라 집니다. 프로그램 /BIND, 되었고 실행 파일에 대 한 기본 주소 및 이미 로드 된 Dll을 사용 하 여 해당 Dll 충돌 하지 않는 경우에 운영 체제를 이러한 주소를 설정 하지 않아도 합니다. 여기서 파일은 올바르게 기반 하지 상황에서는 운영 체제에서 프로그램의 Dll을 재배치 및 프로그램의 로드 시간을 추가 하는 끝점 주소를 다시 계산 합니다.

## <a name="see-also"></a>참고자료

[EDITBIN 옵션](editbin-options.md)

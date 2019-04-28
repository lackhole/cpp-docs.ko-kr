---
title: 링커 도구 경고 LNK4105
ms.date: 11/04/2016
f1_keywords:
- LNK4105
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
ms.openlocfilehash: 880c8519a530f492d0c322575a1386af8a7d0187
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310931"
---
# <a name="linker-tools-warning-lnk4105"></a>링커 도구 경고 LNK4105

'option'; 옵션을 사용 하 여 지정 된 인수 없음 옵션을 무시 합니다.

이 경고에만 발생 경우 합니다 [/LIBPATH](../../build/reference/libpath-additional-libpath.md) 옵션을 설정 합니다. 이 옵션을 사용 하 여 없는 디렉터리를 지정 하는 경우 링커 옵션 무시를이 경고 메시지를 생성 합니다.

기존 환경 라이브러리 설정을 재정의 해야 하는 경우 링커 명령줄에서 /LIBPATH 옵션을 제거 합니다. 라이브러리에 대 한 대체 검색 경로 사용 하려는 경우 /LIBPATH 옵션 다음에 대체 경로 지정 합니다.

## <a name="example"></a>예제

```
link /libpath:c:\filepath\lib bar.obj
```

구문을 사용 하면 링커가의 필수 라이브러리를 검색 하려면 `c:\filepath\lib` 기본 위치에서 검색 하기 전에 합니다.
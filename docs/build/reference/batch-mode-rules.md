---
title: 일괄 처리 모드 규칙
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
ms.openlocfilehash: f01866e347b2734b5adfd111e3ae9de4f9edcf9f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826347"
---
# <a name="batch-mode-rules"></a>일괄 처리 모드 규칙

```
{frompath}.fromext{topath}.toext::
   commands
```

일괄 처리 모드 유추 규칙 N 명령을이 유추 규칙을 통해 이동 하는 경우 유추 규칙의 한 번만 호출을 제공 합니다. 일괄 처리 모드 유추 규칙 없이 n 개의 명령을 호출 해야 합니다. N은 유추 규칙을 트리거하는 종속 항목의 수입니다.

일괄 처리 모드 유추 규칙을 포함 하는 메이크파일 NMAKE 1.62 이상 버전을 사용 해야 합니다. NMAKE 버전을 확인 하려면 1.62 이상을 사용할 수 있는 _NMAKE_VER 매크로 NMAKE 버전을 사용 하 여 실행 합니다. 이 매크로 Visual c + + 제품 버전을 나타내는 문자열을 반환 합니다.

표준 유추 규칙에서만 구문 차이점은 일괄 처리 모드 유추 규칙 이중 콜론 (:)를 사용 하 여 종료 된 것입니다.

> [!NOTE]
>  호출 되는 도구는 여러 파일을 처리할 수 있어야 합니다. 일괄 처리 모드 유추 규칙을 사용 해야 `$<` 종속 파일에 액세스 하는 매크로입니다.

일괄 처리 모드 유추 규칙 빌드 프로세스 속도 수 있습니다. 더 빠르게 일괄 처리에서 컴파일러에 파일을 제공 하려면 때문입니다 컴파일러 드라이버는 한 번만 호출 됩니다. 예를 들어, C 및 c + + 컴파일러 성능이 프로세스 중에 상주 하기 때문에 파일 집합을 처리할 때 더 잘 수행 합니다.

다음 예에서는 일괄 처리 모드 유추 규칙을 사용 하는 방법을 보여 줍니다.

```
#
# sample makefile to illustrate batch-mode inference rules
#
O = .
S = .
Objs = $O/foo1.obj $O/foo2.obj $O/foo2.obj $O/foo3.obj $O/foo4.obj
CFLAGS = -nologo

all : $(Objs)

!ifdef NOBatch
{$S}.cpp{$O}.obj:
!else
{$S}.cpp{$O}.obj::
!endif
   $(CC) $(CFLAGS) -Fd$O\ -c $<

$(Objs) :

#end of makefile
```

NMAKE 일괄 처리 모드 유추 규칙 없이 다음 출력을 생성합니다.

```
E:\tmp> nmake -f test.mak -a NOBatch=1

Microsoft (R) Program Maintenance Utility   Version 7.00.0000
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.
        cl -nologo -Fd.\ -c .\foo1.cpp
foo1.cpp
        cl -nologo -Fd.\ -c .\foo2.cpp
foo2.cpp
        cl -nologo -Fd.\ -c .\foo3.cpp
foo3.cpp
        cl -nologo -Fd.\ -c .\foo4.cpp
foo4.cpp
```

NMAKE의 일괄 처리 모드 유추 규칙을 사용 하 여 다음 결과 생성합니다.

```
E:\tmp> nmake -f test.mak -a

Microsoft (R) Program Maintenance Utility   Version 7.00.0000
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.

        cl -nologo -Fd.\ -c .\foo1.cpp .\foo2.cpp .\foo3.cpp .\foo4.cpp
foo1.cpp
foo2.cpp
foo3.cpp
foo4.cpp
Generating Code...
```

## <a name="see-also"></a>참고자료

[유추 규칙](inference-rules.md)

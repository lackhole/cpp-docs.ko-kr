---
title: 재귀 매크로
description: 재귀 세션에서 NMAKE를 호출 하는 데 사용 하는 매크로에 대해 설명 합니다.
ms.date: 11/20/2019
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
no-loc:
- MAKE
- MAKEDIR
- MAKEFLAGS
ms.openlocfilehash: f2bda23cb079e4fd7d12cea3598d33b3625c088d
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303145"
---
# <a name="recursion-macros"></a>재귀 매크로

재귀 매크로를 사용 하 여 NMAKE를 재귀적으로 호출 합니다. 재귀 세션은 명령줄 및 환경 변수 매크로와 도구 .ini 정보를 상속 합니다. 메이크파일 정의 유추 규칙이 나 `.SUFFIXES` 및 `.PRECIOUS` 사양을 상속 하지 않습니다. 재귀 NMAKE 세션에 매크로를 전달 하는 방법에는 다음 세 가지가 있습니다. 재귀 호출 전에 :::no-loc text="SET"::: 명령을 사용 하 여 환경 변수를 설정 합니다. 명령에서 재귀 호출에 대 한 매크로를 정의 합니다. 또는 도구 .ini에서 매크로를 정의 합니다.

|매크로|정의|
|-----------|----------------|
|**MAKE**|NMAKE를 호출 하는 데 원래 사용 되는 명령입니다.<br /><br /> `$(MAKE)` 매크로는 nmake의 전체 경로를 제공 합니다.|
|**MAKEDIR**|NMAKE를 호출한 경우의 현재 디렉터리입니다.|
|**MAKEFLAGS**|현재 적용 되는 옵션입니다. `/$(MAKEFLAGS)`으로 사용 합니다. **/F** 옵션은 포함 되지 않습니다.|

## <a name="see-also"></a>참고 항목

[특수 NMAKE 매크로](special-nmake-macros.md)

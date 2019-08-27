---
title: 심각한 오류 C1010
ms.date: 08/19/2019
f1_keywords:
- C1010
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
ms.openlocfilehash: 35b0f60f7eb3be887598e7ffaf3e3eae74aefcff
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630792"
---
# <a name="fatal-error-c1010"></a>심각한 오류 C1010

미리 컴파일된 헤더를 찾는 동안 예기치 않은 파일의 끝이 나타났습니다. ' #Include name '을 소스에 추가 하는 것을 잊은 경우

[/Yu](../../build/reference/yu-use-precompiled-header-file.md) 로 지정 된 포함 파일은 소스 파일에 나열 되지 않습니다.  이 옵션은 대부분의 Visual Studio C++ 프로젝트 형식에서 기본적으로 사용 하도록 설정 되며, *pch. h* (visual studio 2017 및 이전 버전의*stdafx.h* )는이 옵션으로 지정 된 기본 포함 파일입니다.

Visual Studio 환경에서 다음 방법 중 하나를 사용 하 여이 오류를 해결 합니다.

- 프로젝트에서 미리 컴파일된 헤더를 사용 하지 않는 경우 **미리 컴파일된 헤더를 사용 하지 않도록**소스 파일의 **미리 컴파일된 헤더 만들기/사용** 속성을 설정 합니다. 이 컴파일러 옵션을 설정 하려면 다음 단계를 수행 합니다.

   1. 프로젝트의 솔루션 탐색기 창에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.

   1. 왼쪽 창에서 **C/C++**  폴더를 클릭 합니다.

   1. **미리 컴파일된 헤더** 노드를 클릭 합니다.

   1. 오른쪽 창에서 **미리 컴파일된 헤더 만들기/사용**을 클릭 한 다음 **미리 컴파일된 헤더 사용 안 함**을 클릭 합니다.

- 현재 프로젝트에서 헤더 파일 (기본적으로 stdafx.h)을 실수로 삭제 하거나 이름을 바꾸거나 제거 하지 않았는지 확인 합니다. 이 파일은 **#include "stdafx.h"** 를 사용 하 여 소스 파일의 다른 코드 앞에도 포함 되어야 합니다. 이 헤더 파일은 파일 프로젝트 속성을 **통해 PCH 만들기/사용** 으로 지정 됩니다.
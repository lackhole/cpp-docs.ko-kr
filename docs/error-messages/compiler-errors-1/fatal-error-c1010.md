---
title: 심각한 오류 C1010
ms.date: 11/04/2016
f1_keywords:
- C1010
helpviewer_keywords:
- C1010
ms.assetid: dfd035f1-a7a2-40bc-bc92-dc4d7f456767
ms.openlocfilehash: 204c7ef94d82513338f6635ec9eb22f26fc090a7
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65448023"
---
# <a name="fatal-error-c1010"></a>심각한 오류 C1010

미리 컴파일된 헤더를 찾는 동안 예기치 않은 파일의 끝이 나타났습니다. 추가 했는지 ' #include 이름 ' 소스에?

지정 된 포함 파일 [/Yu](../../build/reference/yu-use-precompiled-header-file.md) 소스 파일에 나열 되지 합니다.  대부분의 Visual Studio에서 기본적으로이 옵션은 C++ 프로젝트 형식 및 "stdafx.h"가 기본이이 옵션으로 지정 된 파일을 포함 합니다.

Visual Studio 환경에서이 오류를 해결 하려면 다음 방법 중 하나를 사용 합니다.

- 프로젝트에서 미리 컴파일된 헤더를 사용 하지 않는 경우 설정 합니다 **미리 컴파일된 헤더 만들기/사용** 원본 파일의 속성 **사용 하 여 미리 컴파일된 헤더에 없습니다**합니다. 이 컴파일러 옵션을 설정 하려면 다음이 단계를 수행 합니다.

   1. 프로젝트의 솔루션 탐색기 창에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.

   1. 왼쪽된 창에서 클릭 합니다 **C /C++**  폴더입니다.

   1. 클릭 합니다 **미리 컴파일된 헤더** 노드.

   1. 오른쪽 창에서 클릭 **미리 컴파일된 헤더 만들기/사용**를 클릭 하 고 **미리 컴파일된 헤더 사용 안 함**합니다.

- 잘못 삭제, 이름을 바꾸었거나 헤더 파일을 제거 했는지 (기본적으로 stdafx.h) 현재 프로젝트에서. 이 파일을 사용 하 여 소스 파일에서 다른 코드 보다 먼저 포함 될도 해야 **#include "stdafx.h"** 합니다. (이 헤더 파일을 **파일에서 PCH 만들기/사용** 프로젝트 속성)
---
title: 심각한 오류 C1854
ms.date: 11/04/2016
f1_keywords:
- C1854
helpviewer_keywords:
- C1854
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
ms.openlocfilehash: 83eb5e01eac377b8f19a0e94dc1518e3ed557c3b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165645"
---
# <a name="fatal-error-c1854"></a>심각한 오류 C1854

> 개체 파일에 미리 컴파일된 헤더를 만드는 동안 구성 된 정보를 덮어쓸 수 없습니다. '*filename*'

지정한 합니다 [/Yu (미리 컴파일된 헤더 파일 사용)](../../build/reference/yu-use-precompiled-header-file.md) 옵션을 지정한 후 합니다 [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md) 동일한 파일에 대 한 옵션입니다.

이 문제를 해결 하려면 일반적으로 파일 하나만 프로젝트에서 설정 사용 하 여 컴파일해야 하는 **/Yc** 옵션을 사용 하 여 컴파일하는 데 다른 모든 파일을 설정 합니다 **/Yu** 옵션입니다. 사용에 대 한 자세한 내용은 합니다 **/Yc** 옵션과 내용은 Visual Studio IDE에서 설정 하는 방법 [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md)합니다. 미리 컴파일된 헤더 사용에 대 한 자세한 내용은 참조 하세요. [미리 컴파일된 헤더 파일 만들기](../../build/creating-precompiled-header-files.md)합니다.

---
title: 컴파일러 경고(수준 1) C4727
ms.date: 08/19/2019
f1_keywords:
- C4727
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
ms.openlocfilehash: 1bcc029536d2602d50178d7148332b8371db3c7f
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630827"
---
# <a name="compiler-warning-level-1-c4727"></a>컴파일러 경고(수준 1) C4727

Obj_file_1 및 obj_file_2에서 동일한 타임 스탬프를 사용 하는 pch_file 라는 PCH가 있습니다.  첫 번째 PCH 사용.

> [!NOTE]
> Visual Studio 2017이 하 버전에서는 기본적으로 미리 컴파일된 헤더를 *stdafx.h* 라고 하며, visual studio 2019 이상에서는 기본적으로 해당 헤더를 *.pch .h* 라고 합니다.

C4727는 **/yc**를 사용 하 여 여러 compilands을 컴파일하는 경우와 컴파일러가 동일한 .pch 타임 스탬프를 사용 하 여 모든 .obj 파일을 표시할 수 있는 경우 발생 합니다.

이 문제를 해결 하려면 **/yc/c** 를 사용 하 여 소스 파일 하나를 컴파일하고 (pch 생성) 다른 사용자는 **/yu/c** 를 사용 하 여 별도로 컴파일 (pch 사용) 한 다음 함께 연결 합니다.

따라서 다음을 수행 하 고 C4727을 생성 합니다.

::: moniker range="<=vs-2017"

**cl/clr/GL ..cpp b.cpp/Ycstdafx.h**

대신 다음을 수행 합니다.

**cl/clr a. .cpp/Ycstdafx.h/c**

**cl /clr /GL b.cpp c.cpp /Yustdafx.h /link a.obj**

::: moniker-end

::: moniker range=">=vs-2019"

**cl/clr/GL ..cpp b.cpp/Ycpch.h**

대신 다음을 수행 합니다.

**cl/clr a. .cpp/Ycpch.h/c**

**cl/clr/GL b. .cpp/Yupch.h/link. .obj**

::: moniker-end


자세한 내용은 다음을 참조하세요.

- [/Yc(미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md)

- [/Yu(미리 컴파일된 헤더 파일 사용)](../../build/reference/yu-use-precompiled-header-file.md)
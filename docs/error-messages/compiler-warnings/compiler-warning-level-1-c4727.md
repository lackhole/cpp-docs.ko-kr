---
title: 컴파일러 경고(수준 1) C4727
ms.date: 11/04/2016
f1_keywords:
- C4727
helpviewer_keywords:
- C4727
ms.assetid: 991b0087-3a50-40f5-9cdb-cdc367cd472c
ms.openlocfilehash: be1a248fc2709706e137b543344966735c19064e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386436"
---
# <a name="compiler-warning-level-1-c4727"></a>컴파일러 경고(수준 1) C4727

"Pch pch_file obj_file_1 및 obj_file_2 동일한 타임 스탬프를 사용 하 여 합니다.  첫 번째 PCH를 사용합니다.

사용 하 여 여러 번 컴파일할 때 C4727 발생 **/Yc**, 컴파일러에서 동일한.pch 타임 스탬프를 사용 하 여 모든.obj 파일을 표시할 수 없습니다.

를 해결 하려면 사용 하 여 하나의 소스 파일을 컴파일하려면 **/Yc /c** (pch 생성)를 사용 하 여 다른 별도로 컴파일 및 **/Yu /c** (pch 사용)를 함께 연결 합니다.

따라서 다음 않았습니다 하 고 C4727를 생성 하는 경우.

**cl /clr /GL a.cpp b.cpp c.cpp /Ycstdafx.h**

다음을 수행한 대신:

**cl /clr /GL a.cpp /Ycstdafx.h /c**

**cl /clr /GL b.cpp c.cpp /Yustdafx.h /link a.obj**

자세한 내용은 다음 항목을 참조하세요.

- [/Yc(미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md)

- [/Yu(미리 컴파일된 헤더 파일 사용)](../../build/reference/yu-use-precompiled-header-file.md)
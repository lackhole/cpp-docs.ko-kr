---
title: 심각한 오류 C1382
ms.date: 11/04/2016
f1_keywords:
- C1382
helpviewer_keywords:
- C1382
ms.assetid: 7a100f8c-3179-4927-a2f1-98de4c753850
ms.openlocfilehash: 2b7f6fd878f0d0ba6cde19a3a316a01c390e954a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62228566"
---
# <a name="fatal-error-c1382"></a>심각한 오류 C1382

'file' PCH 파일이 'obj' 생성 된 후 다시 작성 되었습니다. 이 개체를 다시 빌드하세요.

사용 하는 경우 [/LTCG](../../build/reference/ltcg-link-time-code-generation.md), 컴파일러가 가리키는 CIL.obj 보다 최신인.pch 파일을 발견 했습니다. CIL.obj 파일의 정보는 만료 됩니다. 개체를 다시 작성 합니다.

로 컴파일하는 경우에 C1382 발생할 수 있습니다 **/Yc**에 컴파일러에 여러 개의 소스 코드 파일 전달 합니다.  를 해결 하려면 사용 하지 말고 **/Yc** 컴파일러에 여러 개의 소스 코드 파일을 전달 하는 경우.  자세한 내용은 [/Yc (미리 컴파일된 헤더 파일 만들기)](../../build/reference/yc-create-precompiled-header-file.md)합니다.
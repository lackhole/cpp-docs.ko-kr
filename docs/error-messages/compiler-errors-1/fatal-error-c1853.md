---
title: 심각한 오류 C1853
ms.date: 11/04/2016
f1_keywords:
- C1853
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
ms.openlocfilehash: ec2d6bf6bac46cca8bdc2e3b8fe7cc6b7799d78a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165920"
---
# <a name="fatal-error-c1853"></a>심각한 오류 C1853

> '*filename*' 미리 컴파일된 헤더 파일이 이전 버전의 컴파일러에서에서 또는 미리 컴파일된 헤더를 C++ C에서 (또는 그 반대로) 사용 하 고

가능한 원인:

- 미리 컴파일된 헤더는 이전 컴파일러 버전을 사용 하 여 컴파일 되었습니다. 다시 현재 컴파일러를 사용 하 여 헤더를 컴파일하십시오.

- 미리 컴파일된 헤더는 C++ 에서 C 사용 하 여 사용에 대 한 헤더 중 하나를 지정 하 여 사용 하 고는 [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) 컴파일러 옵션 또는 소스 파일의 접미사 "c"로 변경 합니다. 자세한 내용은 [미리 컴파일 코드에 대 한 두 가지 선택](../../build/creating-precompiled-header-files.md#two-choices-for-precompiling-code)합니다.
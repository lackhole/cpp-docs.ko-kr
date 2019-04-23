---
title: C++릴리스 빌드-Visual Studio
ms.date: 12/10/2018
helpviewer_keywords:
- debugging [C++], release builds
- release builds
- debug builds, converting to release build
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
ms.openlocfilehash: cf11e63354502be000ba5f7259d9e36dfa774060
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038164"
---
# <a name="release-builds"></a>릴리스 빌드

릴리스 빌드에는 최적화를 사용합니다. 최적화를 사용하여 릴리스 빌드를 만들 경우 컴파일러가 기호화된 디버깅 정보를 생성하지 않습니다. 기호화된 디버깅 정보가 없고 TRACE 및 ASSERT 호출에 대한 코드가 생성되지 않으면 실행 파일의 크기가 줄어들고 따라서 속도가 더 빨라지게 됩니다.

## <a name="in-this-section"></a>단원 내용

[릴리스 빌드를 만들 때의 일반적인 문제](common-problems-when-creating-a-release-build.md)<br/>
[릴리스 빌드 문제 해결](fixing-release-build-problems.md)<br/>
[ASSERT 대신 VERIFY 사용](using-verify-instead-of-assert.md)<br/>
[디버그 빌드를 사용한 메모리 덮어쓰기 확인](using-the-debug-build-to-check-for-memory-overwrite.md)<br/>
[방법: 릴리스 빌드 디버그](how-to-debug-a-release-build.md)<br/>
[메모리 덮어쓰기 확인](checking-for-memory-overwrites.md)<br/>
[코드 최적화](optimizing-your-code.md)<br/>

## <a name="see-also"></a>참고자료

[C/C++ 빌드 참조](reference/c-cpp-building-reference.md)
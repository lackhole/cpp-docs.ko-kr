---
title: 컴파일러 오류 C2026
ms.date: 11/04/2016
f1_keywords:
- C2026
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
ms.openlocfilehash: da4c03c681f95efaa5edb159869315b41d027e99
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303530"
---
# <a name="compiler-error-c2026"></a>컴파일러 오류 C2026

문자열이 너무 길어 잘립니다. 후행 문자

문자열 16380 싱글바이트 문자의 제한 보다 긴 경우

인접 문자열을 연결 하기 전에 문자열 16380 싱글바이트 자 보다 길 수 없습니다.

유니코드 문자열 길이의 절반이는 또한이 오류를 생성 합니다.

다음과 같이 정의 된 문자열에 있는 경우 C2026 생성 됩니다.

```
char sz[] =
"\
imagine a really, really \
long string here\
";
```

손상 시킬 수 있습니다이 다음과 같이 합니다.

```
char sz[] =
"\
imagine a really, really "
"long string here\
";
```

하려는 매우 큰 문자열 리터럴 (32k 이상)를 저장할 사용자 지정 리소스 또는 외부 파일입니다. 참조 [새 사용자 지정 또는 데이터 리소스 만들기](../../windows/creating-a-new-custom-or-data-resource.md) 자세한 내용은 합니다.
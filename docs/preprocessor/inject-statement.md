---
title: inject_statement
ms.date: 10/18/2018
f1_keywords:
- inject_statement
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
ms.openlocfilehash: 237ca796028aad7aff55442eb2806fe400330a29
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383726"
---
# <a name="injectstatement"></a>inject_statement

**C++특정**

소스 텍스트로서 인수를 형식 라이브러리 헤더에 삽입합니다.

## <a name="syntax"></a>구문

```
inject_statement("source_text")
```

### <a name="parameters"></a>매개 변수

*source_text*<br/>
형식 라이브러리 헤더 파일에 삽입되는 소스 텍스트입니다.

## <a name="remarks"></a>설명

헤더 파일의 형식 라이브러리 내용을 래핑하는 네임스페이스 선언의 시작 부분에 텍스트가 배치됩니다.

**최종 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import Directive](../preprocessor/hash-import-directive-cpp.md)
---
title: execution_character_set
ms.date: 10/18/2018
f1_keywords:
- execution_character_set
- vc-pragma.execution_character_set
helpviewer_keywords:
- pragma execution_character_set
ms.assetid: 32248cbc-7c92-4dca-8442-230c052b53ad
ms.openlocfilehash: bd31e8e91a1bcbfa6ace9b47fa2b13dd945adb20
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039928"
---
# <a name="executioncharacterset"></a>execution_character_set

문자열 및 문자 리터럴에 사용 되는 실행 문자 집합을 지정 합니다. U8 접두사가 있는 표시 된 리터럴에 대 한이 지시문이 필요 하지 않습니다.

## <a name="syntax"></a>구문

```
#pragma execution_character_set("target")
```

### <a name="parameters"></a>매개 변수

*target*<br/>
대상 실행 문자 집합을 지정합니다. 현재 집합이 지원만 대상 실행은 "utf-8"입니다.

## <a name="remarks"></a>설명

컴파일러 지시문이 Visual Studio 2015 업데이트 2부터 사용 되지 않습니다. 사용 하는 것이 좋습니다는 `/execution-charset:utf-8` 또는 `/utf-8` 를 사용 하 여 함께 컴파일러 옵션을 `u8` 확장된 문자를 포함 하는 좁은 문자 및 문자열 리터럴에 접두사입니다. 에 대 한 자세한 내용은 합니다 `u8` 접두사를 참조 하십시오 [문자열 및 문자 리터럴](../cpp/string-and-character-literals-cpp.md)합니다. 컴파일러 옵션에 대 한 자세한 내용은 참조 하세요. [(실행 문자 집합 설정) /execution-charset](../build/reference/execution-charset-set-execution-character-set.md) 하 고 [/utf-8 (소스 및 실행 문자 집합을 u t F-8)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)합니다.

`#pragma execution_character_set("utf-8")` 지시문 인코딩할 좁은 문자 및 소스 코드의 좁은 문자열 리터럴 u t F-8로 실행 파일에서 컴파일러에 지시 합니다. 이 출력 인코딩 무관 소스 파일 인코딩을 사용 합니다.

기본적으로 컴파일러는 실행 문자 집합으로 현재 코드 페이지를 사용 하 여 좁은 문자 및 좁은 문자열 인코딩합니다. 이 유니코드 또는 DBCS 문자 리터럴 현재 코드 페이지의 범위를 벗어나는 변환한 출력에서 기본 대체 문자를 의미 합니다. 낮은 순서 바이트의 유니코드 및 DBCS 문자는 잘립니다. 거의 확실히 원하지 않는 경우 사용 하 여 소스 파일의 리터럴에 대 한 utf-8 인코딩을 지정할 수 있습니다는 `u8` 접두사입니다. 컴파일러는 그대로 출력에 이러한 u t F-8로 인코딩된 문자열을 전달 합니다. 좁은 문자 리터럴 접두사로 u8 사용 1 바이트에 맞아야 합니다. 또는 출력에서 잘립니다.

기본적으로 Visual Studio 출력에 대 한 소스 코드를 해석 하는 데 사용 하는 소스 문자 집합으로 현재 코드 페이지를 사용 합니다. 파일을 읽으면 파일 코드 페이지를 설정 하지 않으면 또는 파일의 시작 부분에서 바이트 순서 표시 (BOM) 또는 u t F-16 자는 검색 하지 않는 한 Visual Studio는 현재 코드 페이지에 따라 것을 해석 합니다. 자동 검색을 BOM 없이 u t F-8로 인코드된 소스 파일에서 발견 한 경우에 현재 코드 페이지와 u t F-8를 설정할 수 없어, Visual Studio는 현재 코드 페이지를 사용 하 여 인코딩됩니다 가정 합니다. 범위 밖에 있는 경우 지정 된 또는 자동으로 검색 된 코드 페이지 컴파일러 경고 및 오류가 발생할 수는 소스 파일의 문자입니다.

## <a name="see-also"></a>참고자료

[Pragma 지시문 및 \_ \_Pragma 키워드](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[/execution-charset (실행 문자 집합 설정)](../build/reference/execution-charset-set-execution-character-set.md)<br/>
[/utf-8 (소스 및 실행 문자 집합을 u t F-8)](../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)
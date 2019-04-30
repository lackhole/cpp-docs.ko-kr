---
title: /Fi (출력 파일 이름 전처리)
ms.date: 11/04/2016
f1_keywords:
- /Fi
helpviewer_keywords:
- Fi compiler option (C++)
- -Fi compiler option (C++)
- /Fi compiler option (C++)
- preprocessing output files, file name
ms.assetid: 6d0ba983-a8b7-41ec-84f5-b4688ef8efee
ms.openlocfilehash: 990c48a72c3f6017d893ddf9b46bcbb737bfb634
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271257"
---
# <a name="fi-preprocess-output-file-name"></a>/Fi (출력 파일 이름 전처리)

출력 파일의 이름을 지정 합니다 [/P (파일로 전처리)](p-preprocess-to-a-file.md) 컴파일러 옵션 전처리 된 출력을 씁니다.

## <a name="syntax"></a>구문

```
/Fipathname
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`pathname`|생성 된 출력 파일의 경로 이름을 합니다 **/P** 컴파일러 옵션입니다.|

## <a name="remarks"></a>설명

사용 합니다 **/Fi** 함께에서 컴파일러 옵션을 **/P** 컴파일러 옵션입니다.

에 대 한 경로 지정 하는 경우는 `pathname` 매개 변수, 즉 기본 원본 파일의 전처리 된 출력 파일의 기본 이름으로 사용 됩니다. `pathname` 매개 변수는 특정 파일 이름 확장명을 사용 하지 않아도 됩니다. 그러나 ".i"의 확장 파일 이름 확장명을 지정 하지 않는 경우 사용 됩니다.

## <a name="example"></a>예제

다음 명령줄 주석을 유지, 추가 PROGRAM.cpp 전처리 [#line](../../preprocessor/hash-line-directive-c-cpp.md) 지시문 MYPROCESS.i 파일로 결과 기록 합니다.

```
CL /P /FiMYPROCESS.I PROGRAM.CPP
```

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[/P(파일로 전처리)](p-preprocess-to-a-file.md)<br/>
[경로 이름 지정](specifying-the-pathname.md)

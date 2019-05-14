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

[/P (파일로 전처리)](p-preprocess-to-a-file.md) 컴파일러 옵션이 전처리 된 출력을 쓰는 출력 파일의 이름을 지정 합니다

## <a name="syntax"></a>구문

```
/Fipathname
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|`pathname`|**/P** 컴파일러 옵션으로 생성 된 출력 파일의 경로와 이름 입니다.|

## <a name="remarks"></a>설명

컴파일러 옵션 **/Fi**와 **/P**를 함께 사용합니다.

`pathname` 매개 변수에 대한 경로만 지정하면 소스파일의 기본 이름이 전처리된 출력 파일의 기본 이름으로 사용됩니다. `pathname` 매개 변수에는 특정 파일이름 확장자가 필요하지 않습니다. 확장자를 지정하지 않으면 ".i"의 확장자가 부여됩니다.

## <a name="example"></a>예제

다음 명령줄은 PROGRAM.cpp를 전처리하고, 주석을 보존한 후 [#line](../../preprocessor/hash-line-directive-c-cpp.md) 지시문을 추가한 다음 MYPROCESS.i 파일에 결과를 기록 합니다.

```
CL /P /FiMYPROCESS.I PROGRAM.CPP
```

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 옵션](compiler-options.md)<br/>
[/P(파일로 전처리)](p-preprocess-to-a-file.md)<br/>
[경로 이름 지정](specifying-the-pathname.md)

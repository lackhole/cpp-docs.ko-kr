---
title: 리소스 컴파일러 오류 RC2104
ms.date: 11/04/2016
f1_keywords:
- RC2104
helpviewer_keywords:
- RC2104
ms.assetid: 792a3bd8-cb4c-4817-b288-4ce37082b582
ms.openlocfilehash: 6ac1786e795c0c8ed57af2d341f43b8ba39229c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346563"
---
# <a name="resource-compiler-error-rc2104"></a>리소스 컴파일러 오류 RC2104

정의되지 않은 키워드 또는 키 이름: 키

지정한 키워드 또는 키 이름이 정의되지 않았습니다.

이 오류는 리소스 정의 또는 포함된 헤더 파일의 오타로 인해 발생하는 경우가 많습니다. 헤더 파일이 없어도 발생할 수 있습니다.

문제를 해결하려면 정의된 키워드 또는 키 이름을 포함해야 하는 헤더 파일을 찾은 다음 리소스 파일에 해당 이름이 포함되어 있으며 키워드 또는 키 이름의 철자가 올바른지 확인합니다. 미리 컴파일된 헤더를 사용하여 프로젝트를 만든 후 제거한 경우에는 리소스 파일에 아직 필요한 헤더가 포함되어 있는지 확인합니다.

정의 된 키워드 및 Visual Studio에서 리소스 파일에서 키 이름을 확인 하려면 엽니다는 **리소스 뷰** 창-메뉴 모음에서 **뷰**에 **리소스 뷰**-및 그런 다음.rc 파일에 대 한 바로 가기 메뉴를 열고 선택 **리소스 기호** 정의 된 기호 목록을 볼 수 있습니다. 포함된 된 헤더를 수정 하려면.rc 파일에 대 한 바로 가기 메뉴를 열고 선택한 **리소스 내용**합니다.

다음 메시지가 표시되는 경우

```
undefined keyword or key name: MFT_STRING
```

\MCL\MFC\Include\AfxRes.h를 열고 아래 include 지시문을 추가합니다.

```
#include <winresrc.h>
```
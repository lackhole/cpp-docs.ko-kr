---
title: 인라인 파일 텍스트 만들기
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
ms.openlocfilehash: a45aa526ca99af93cda86a2a8e0580d4d036ca6d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826482"
---
# <a name="creating-inline-file-text"></a>인라인 파일 텍스트 만들기

인라인 파일은 임시 또는 영구입니다.

## <a name="syntax"></a>구문

```
inlinetext
.
.
.
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>설명

지정할 *inlinetext* 명령은 첫 번째 줄에서 합니다. 개별 줄의 시작 부분에 이중 꺾쇠괄호(<<)를 사용해서 끝을 표시합니다. 모든 파일 포함 *inlinetext* 대괄호 구분 하기 전에 합니다. 합니다 *inlinetext* 매크로 확장 및 대체 있지만 지시문 또는 메이크파일 주석은 있을 수 있습니다. 공백, 탭 및 줄 바꿈 문자 리터럴로 처리 됩니다.

임시 파일을 세션의 기간 존재 하며 다른 명령을 사용 하 여 다시 사용할 수 있습니다. 지정할 **유지** NMAKE 세션 후 파일을 유지 하려면 닫는 꺾쇠 괄호 뒤 명명 되지 않은 파일을 생성 된 파일 이름으로 디스크에 유지 됩니다. 지정할 **NOKEEP** 또는 임시 파일에 대 한 것입니다. **유지할** 하 고 **NOKEEP** 대/소문자 구분 없는 합니다.

## <a name="see-also"></a>참고자료

[메이크파일의 인라인 파일](inline-files-in-a-makefile.md)

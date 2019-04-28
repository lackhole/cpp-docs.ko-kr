---
title: 모듈 정의 문의 규칙
ms.date: 11/04/2016
f1_keywords:
- .def
helpviewer_keywords:
- module definition files, statement syntax
- module definition files
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
ms.openlocfilehash: f6269ad2d5bf3952e485f2ca5e5d1f411c5f1e0c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318513"
---
# <a name="rules-for-module-definition-statements"></a>모듈 정의 문의 규칙

다음 구문 규칙이.def 파일의 모든 문이 적용 됩니다. 각 문을 사용 하 여 특정 문에 적용 되는 다른 규칙과 같습니다.

- 문, 특성 키워드 및 사용자 지정 식별자는 대/소문자 구분 합니다.

- 긴 파일 공백 또는 세미콜론 (;)를 포함 하는 이름은 큰따옴표 (")로 묶어야 합니다.

- 문 키워드 인수에서 분리 하는 데 서로 문을 구분 하나 이상의 공백, 탭 또는 줄 바꿈 문자를 사용 합니다. 콜론 (:) 또는 등호 (=) 인수를 지정 하는 0 또는 자세한 공백, 탭 또는 줄 바꿈 문자 둘러싸여 있습니다.

- A **이름을** 하거나 **라이브러리** 문을 사용 하는 경우 앞에 야 다른 모든 문의 합니다.

- 합니다 **섹션** 하 고 **내보내기** 문을.def 파일에 두 번 이상 나타날 수 있습니다. 각 문은 하나 이상의 공백, 탭 또는 줄 바꿈 문자 구분 해야 하는 여러 사양 걸릴 수 있습니다. 문 키워드 첫 번째 지정 하기 전에 한 번 나타나야 하며 각 추가 사양 앞에서 반복 될 수 있습니다.

- 많은 문에 해당 하는 링크 명령줄 옵션이 있을 합니다. 자세한 내용은 해당 링크 옵션의 설명을 참조 하세요.

- .Def 파일의 주석을 세미콜론 (;)으로 지정 된 각 주석 줄의 시작 부분입니다. 주석 줄을 문을 사용 하 여 공유할 수 없지만 여러 줄 문에서 사양 사이 나타날 수 있습니다. (**섹션** 하 고 **내보내기를** 여러 줄 문의 합니다.)

- 숫자 인수는 10 진수로 지정 또는 16 진수입니다.

- 문자열 인수를 일치 하는 경우는 [예약어](reserved-words.md), 큰따옴표 (")에 묶어야 합니다.

## <a name="see-also"></a>참고자료

[모듈 정의(.Def) 파일](module-definition-dot-def-files.md)

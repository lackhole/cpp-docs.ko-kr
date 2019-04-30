---
title: SECTIONS(C/C++)
ms.date: 11/04/2016
f1_keywords:
- SECTIONS
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
ms.openlocfilehash: 5125b09675969c784aafe375faf1fdbc36d8c5d9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62318630"
---
# <a name="sections-cc"></a>SECTIONS(C/C++)

하나 이상의 섹션이 `definitions` 프로젝트의 출력 파일 섹션에에서 대 한 액세스 지정자는 합니다.

```
SECTIONS
definitions
```

## <a name="remarks"></a>설명

각 정의는 별도의 줄에 있어야 합니다. `SECTIONS` 키워드 앞의 줄에서 첫 번째 정의와 동일한 줄에 있을 수 있습니다. .Def 파일에는 하나 이상 포함 될 수 있습니다 `SECTIONS` 문입니다.

이 `SECTIONS` 문을 이미지 파일에서 하나 이상의 섹션에 대 한 특성을 설정 하 고 섹션의 각 형식에 대 한 기본 특성을 재정의할 수 있습니다.

형식은 `definitions` 됩니다.

`.section_name specifier`

여기서 `.section_name` 은 프로그램 이미지의 섹션의 이름 및 `specifier` 하나 이상의 다음 액세스 한정자는:

|한정자|설명|
|--------------|-----------------|
|`EXECUTE`|섹션을 실행할 수 있습니다.|
|`READ`|데이터에서 읽을 수 있습니다.|
|`SHARED`|이미지를 로드 하는 모든 프로세스에서 섹션을 공유 합니다.|
|`WRITE`|데이터를 쓸 수 있습니다.|

지정자 이름을 공백으로 구분 합니다. 예를 들어:

```
SECTIONS
.rdata READ WRITE
```

`SECTIONS` 섹션 목록 시작 부분을 표시 `definitions`합니다. 각 `definition` 별도 줄에 있어야 합니다. 합니다 `SECTIONS` 키워드는 첫 번째 같은 줄에 있을 수 있습니다 `definition` 앞의 줄 또는 합니다. .Def 파일에는 하나 이상 포함 될 수 있습니다 `SECTIONS` 문입니다. 합니다 `SEGMENTS` 키워드에 대 한 동의어로 사용할 `SECTIONS`합니다.

시각적 개체의 이전 버전 C++ 지원:

```
section [CLASS 'classname'] specifier
```

`CLASS` 키워드는 호환성을 위해 지원 되지만 무시 됩니다.

해당 섹션 특성 지정 방법은 합니다 [섹션/](section-specify-section-attributes.md) 옵션입니다.

## <a name="see-also"></a>참고자료

[모듈 정의 문의 규칙](rules-for-module-definition-statements.md)

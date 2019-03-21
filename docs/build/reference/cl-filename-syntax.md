---
title: CL 파일 이름 구문
ms.date: 11/04/2016
f1_keywords:
- cl
helpviewer_keywords:
- syntax, compiler filename
- paths, CL compiler filename syntax
- cl.exe compiler, filename syntax
- extensions, specifying to compiler
- file names [C++], CL compiler
- file names [C++]
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
ms.openlocfilehash: b20f88e69c6e0d1774f1cd81b3ee833c4f0ff696
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811773"
---
# <a name="cl-filename-syntax"></a>CL 파일 이름 구문

CL은 FAT, HPFS 또는 NTFS 명명 규칙을 따르는 이름이 지정된 파일을 허용합니다. 파일 이름은 전체 또는 부분 경로를 포함할 수 있습니다. 전체 경로에는 드라이브 이름과 디렉터리 이름 하나 이상이 포함됩니다. Cl 파일 이름 백슬래시 구분 (\\) 또는 슬래시 (/). 공백이 있는 파일 이름은 큰따옴표 문자로 묶어야 합니다. 부분 경로에서는 드라이브 이름이 생략됩니다. 이 경우 CL은 드라이브를 현재 드라이브로 가정합니다. 경로를 지정하지 않으면 CL은 파일이 현재 디렉터리에 있다고 가정합니다.

파일 이름 확장명에 따라 파일 처리 방법이 결정됩니다. 확장명이 .c, .cxx 또는 .cpp인 C 파일 및 C++ 파일은 컴파일됩니다. .obj 파일, 라이브러리(.lib) 및 모듈 정의(.def) 파일은 처리되지 않고 링커로 전달됩니다.

## <a name="see-also"></a>참고자료

[MSVC 컴파일러 명령줄 구문](compiler-command-line-syntax.md)

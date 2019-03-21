---
title: 모듈 정의(.Def) 파일
ms.date: 11/04/2016
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
ms.openlocfilehash: 0047f24722644cd9a68bbbf827ced26ad085d4c1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812241"
---
# <a name="module-definition-def-files"></a>모듈 정의(.Def) 파일

모듈 정의(.def) 파일은 내보내기 정보, 특성 및 링크되는 프로그램에 대한 기타 정보를 링커에 제공합니다. .def 파일은 DLL을 빌드할 때 가장 유용합니다. 있기 때문에 [MSVC 링커 옵션](linker-options.md) 사용할 수 있는 모듈 정의 문의 대신.def 파일 일반적으로 필요 하지 않습니다. 내보내는 함수를 지정하기 위한 방법으로 [__declspec(dllexport)](../exporting-from-a-dll-using-declspec-dllexport.md)을 사용할 수도 있습니다.

링커 단계에서 링커 옵션 [/DEF(모듈 정의 파일 지정)](def-specify-module-definition-file.md)를 사용하여 .def 파일을 호출할 수 있습니다.

내보내기가 없는 .exe 파일을 빌드하는 경우 .def 파일을 사용하면 출력 파일의 크기가 커지고 로드 속도는 느려지게 됩니다.

예제를 보려면 [DEF 파일을 사용하여 DLL에서 내보내기](../exporting-from-a-dll-using-def-files.md)를 참조하세요.

자세한 내용은 다음 단원을 참조하세요.

- [모듈 정의 문의 규칙](rules-for-module-definition-statements.md)

- [EXPORTS](exports.md)

- [HEAPSIZE](heapsize.md)

- [LIBRARY](library.md)

- [Name](name-c-cpp.md)

- [SECTIONS](sections-c-cpp.md)

- [STACKSIZE](stacksize.md)

- [STUB](stub.md)

- [VERSION](version-c-cpp.md)

- [예약어](reserved-words.md)

## <a name="see-also"></a>참고자료

[C/C++ 빌드 참조](c-cpp-building-reference.md)<br/>
[MSVC 링커 옵션](linker-options.md)

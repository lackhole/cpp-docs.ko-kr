---
title: __unaligned
ms.date: 12/17/2018
f1_keywords:
- __unaligned_cpp
- __unaligned
- _unaligned
helpviewer_keywords:
- __unaligned keyword [C++]
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
ms.openlocfilehash: 8eb1b93aa55601125600b6c69d9bff3d9ca43aa3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62244118"
---
# <a name="unaligned"></a>__unaligned

**Microsoft 전용**합니다. 포인터를 선언 하는 경우는 **__unaligned** 한정자, 컴파일러는 포인터가 정렬 되지 않은 데이터의 주소 지정 합니다. 따라서 플랫폼에 적절 한 코드 정렬 되지 않은 읽기를 처리 하도록 생성 되 고 포인터를 통해 씁니다.

## <a name="remarks"></a>설명

이 한정자에는 포인터가; 데이터의 맞춤을 설명 합니다. 포인터 자체는 정렬로 간주 됩니다.

에 대 한 필요성을 **__unaligned** 키워드 플랫폼과 환경에 따라 다릅니다. 데이터를 적절 하 게 표시할 오류 성능 저하의 하드웨어 오류에 이르는 다양 한 문제가 발생할 수 있습니다. 합니다 **__unaligned** 한정자 x86에 대해 올바르지 않습니다. 플랫폼입니다.

이전 버전과 호환성에 대 한 **_unaligned** 에 대 한 동의어가 **__unaligned** 하지 않으면 컴파일러 옵션 [/Za \(언어 확장 사용 안 함)](../build/reference/za-ze-disable-language-extensions.md) 지정 됩니다.

정렬에 대한 자세한 내용은 다음을 참조하십시오.

- [align(C++)](../cpp/align-cpp.md)

- [__alignof 연산자](../cpp/alignof-operator.md)

- [pack](../preprocessor/pack.md)

- [/Zp(구조체 멤버 맞춤)](../build/reference/zp-struct-member-alignment.md)

- [구조체 맞춤 예제](../build/x64-software-conventions.md#examples-of-structure-alignment)

## <a name="see-also"></a>참고자료

[C++ 키워드](../cpp/keywords-cpp.md)
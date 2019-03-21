---
title: ASSERT 대신 VERIFY 사용
ms.date: 11/04/2016
f1_keywords:
- assert
helpviewer_keywords:
- ASSERT statements
- debugging [MFC], ASSERT statements
- VERIFY macro
- assertions, troubleshooting ASSERT statements
- debugging assertions
- assertions, debugging
ms.assetid: 4c46397b-3fb1-49c1-a09b-41a72fae3797
ms.openlocfilehash: e6903616f8b4250b3d67db333be4fc17e8328952
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826334"
---
# <a name="using-verify-instead-of-assert"></a>ASSERT 대신 VERIFY 사용

MFC 응용 프로그램의 디버그 버전을 실행 하는 경우는 문제가 없다고 가정 합니다. 그러나 동일한 응용 프로그램의 릴리스 버전 충돌, 잘못 된 결과 반환 및/또는 다른 몇 가지 비정상적인 동작을 수행 합니다.

올바르게 수행 되는지 확인 하는 ASSERT 문을에 중요 한 코드를 배치 하면이 문제를 발생할 수 있습니다. ASSERT 문은 MFC 프로그램의 릴리스 빌드에 주석 때문에 릴리스 빌드에서 코드 실행 되지 않습니다.

ASSERT 함수 호출이 성공 했는지 확인 하려면를 사용 하는 경우 사용을 고려 [확인](../mfc/reference/diagnostic-services.md#verify) 대신 합니다. VERIFY 매크로 모두 디버그에서 자체 인수를 평가 하 고 응용 프로그램의 릴리스 빌드.

다른 좋은 방법은 함수의 반환 값을 임시 변수에 할당 한 다음 ASSERT 문에서 변수를 테스트 합니다.

다음 코드 조각은 검사 합니다.

```
enum {
    sizeOfBuffer = 20
};
char *buf;
ASSERT(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

이 코드는 MFC 응용 프로그램의 디버그 버전에서 완벽 하 게 실행 됩니다. 경우에 대 한 호출 `calloc( )` 실패 하면 파일 및 줄 번호를 포함 하는 진단 메시지가 표시 됩니다. 그러나 일반 정품 빌드에서 MFC 응용 프로그램:

- 에 대 한 호출 `calloc( )` 발생 하지 않으며, 종료 `buf` 초기화 되지 않은 또는

- `strcpy_s( )` 복사 "`Hello, World`" 메모리, 가능한 경우 응용 프로그램 충돌 또는 응답을 중지 하려면 시스템의 임의 부분에 또는

- `free()` 할당 되지 않은 메모리를 확보 하려고 시도 합니다.

ASSERT를 올바르게 사용 하려면 다음과 코드 샘플을 변경 해야 합니다.

```
enum {
    sizeOfBuffer = 20
};
char *buf;
buf = (char *) calloc(sizeOfBuffer, sizeof(char) );
ASSERT( buf != NULL );
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

또는 확인을 대신 사용할 수 있습니다.

```
enum {
    sizeOfBuffer = 20
};
char *buf;
VERIFY(buf = (char *) calloc(sizeOfBuffer, sizeof(char) ));
strcpy_s( buf, sizeOfBuffer, "Hello, World" );
free( buf );
```

## <a name="see-also"></a>참고자료

[릴리스 빌드 문제 해결](fixing-release-build-problems.md)

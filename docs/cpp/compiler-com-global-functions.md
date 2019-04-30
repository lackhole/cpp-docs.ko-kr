---
title: 컴파일러 COM 전역 함수
ms.date: 11/04/2016
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
ms.openlocfilehash: ac74270cd020aa66ccc14ff314a00b388a038086
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399189"
---
# <a name="compiler-com-global-functions"></a>컴파일러 COM 전역 함수

**Microsoft 전용**

다음 루틴을 사용할 수 있습니다.

|함수|설명|
|--------------|-----------------|
|[_com_raise_error](../cpp/com-raise-error.md)|Throw 된 [_com_error](../cpp/com-error-class.md) 오류에 대 한 응답에서입니다.|
|[_set_com_error_handler](../cpp/set-com-error-handler.md)|COM 오류 처리에 사용되는 기본 함수를 대체합니다.|
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|`BSTR` 값을 `char *` 형식으로 변환합니다.|
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|`char *` 값을 `BSTR` 형식으로 변환합니다.|

**Microsoft 전용 종료**

## <a name="see-also"></a>참고자료

[컴파일러 COM 지원 클래스](../cpp/compiler-com-support-classes.md)<br/>
[컴파일러 COM 지원](../cpp/compiler-com-support.md)
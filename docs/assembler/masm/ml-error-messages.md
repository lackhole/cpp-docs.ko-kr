---
title: ML 오류 메시지
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
ms.openlocfilehash: b9238591ae025c4af258d8b5feda6e05c8bd291b
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74397191"
---
# <a name="ml-error-messages"></a>ML 오류 메시지

MASM 구성 요소에 의해 생성 된 오류 메시지는 다음 세 가지 범주로 나뉩니다.

- **오류가 발생 했습니다.** 이는 유틸리티가 일반적인 프로세스를 완료 하지 못하도록 하는 심각한 문제를 의미 합니다.

- **심각 하지 않은 오류입니다.** 이 유틸리티는 프로세스를 완료할 수 있습니다. 이 경우에는 원하는 결과가 아닐 수 있습니다.

- **기록.** 이러한 메시지는 원하는 결과를 얻을 수 없도록 하는 조건을 표시 합니다.

모든 오류 메시지에는 다음과 같은 형식이 사용 됩니다.

> *유틸리티*: *파일 이름* (*줄*): {*Error_type*} (*코드*): *Message_text*

여기서

*유틸리티*\
오류 메시지를 보낸 프로그램입니다.

*파일 이름*\
오류 생성 조건을 포함 하는 파일입니다.

*줄*\
오류 조건이 있는 대략적인 줄입니다.

*Error_type*\
심각한 오류, 오류 또는 경고입니다.

*코드*\
고유 5 자리 또는 6 자리 오류 코드입니다.

*Message_text*\
오류 조건에 대 한 짧고 일반적인 설명입니다.

## <a name="see-also"></a>참고 항목

[Microsoft 매크로 어셈블러 참조](../../assembler/masm/microsoft-macro-assembler-reference.md)

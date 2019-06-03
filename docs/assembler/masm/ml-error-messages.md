---
title: ML 오류 메시지
ms.date: 08/30/2018
ms.topic: error-reference
f1_keywords:
- vc.errors.ml
helpviewer_keywords:
- MASM (Microsoft Macro Assembler), ML error messages
ms.assetid: e7e164b3-6d65-4b5b-8925-bfbebc043523
ms.openlocfilehash: adf2c509c3d8d9110ddb757f809a4bca9199df7a
ms.sourcegitcommit: af580f3a11b19d22288424eac7ceae1bc24ab312
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66355322"
---
# <a name="ml-error-messages"></a>ML 오류 메시지

MASM 구성 요소에 의해 생성 된 오류 메시지를 다음과 같은 세 가지 범주로 분류 됩니다.

- **심각한 오류입니다.** 이러한 유틸리티의 일반적인 프로세스를 완료 하지 못하도록 하는 심각한 문제를 나타냅니다.

- **치명적이 지 않은 오류가 발생 했습니다.** 유틸리티를 해당 프로세스를 완료할 수 있습니다. 이 경우 해당 결과가 원하는 일 수 되지 않습니다.

- **경고입니다.** 이러한 메시지에는 원하는 결과 받지 못할 수도 있다는 조건을 나타냅니다.

다음 형식을 사용 하는 모든 오류 메시지:

> *유틸리티*: *Filename* (*줄*): {*Error_type*} (*코드*): *Message_text*

다음은 각 문자에 대한 설명입니다.

*유틸리티*<br/>
오류 메시지를 전송 하는 프로그램입니다.

*Filename*<br/>
오류 생성 조건을 포함 하는 파일입니다.

*Line*<br/>
오류 조건이 있는 대략적인 줄.

*Error_type*<br/>
심각한 오류, 오류 또는 경고입니다.

*코드*<br/>
고유 5 또는 6 숫자 오류 코드입니다.

*Message_text*<br/>
오류 조건 및 간단한 설명입니다.

## <a name="see-also"></a>참고자료

[Microsoft 매크로 어셈블러 참조](../../assembler/masm/microsoft-macro-assembler-reference.md)

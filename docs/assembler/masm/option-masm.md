---
title: OPTION (MASM)
ms.date: 08/30/2018
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: 0f90ab0115c3dde894d468bbbe60ffa0193b8336
ms.sourcegitcommit: 9ee5df398bfd30a42739632de3e165874cb675c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74395175"
---
# <a name="option-masm"></a>OPTION (MASM)

어셈블러의 기능을 사용 하거나 사용 하지 않도록 설정 합니다.

## <a name="syntax"></a>구문

> **옵션 옵션** *목록*

## <a name="remarks"></a>주의

사용할 수 있는 옵션은 다음과 같습니다.

|||||
|-|-|-|-|
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**에뮬레이터**|
|**NOEMULATOR**|**에필로그**|**EXPR16**|**EXPR32**|
|**언어도**|**LJMP**|**NOLJMP**|**M510**|
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**이동**|
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|
|**PROC**|**프롤로그**|**READONLY**|**NOREADONLY**|
|**범위**|**NOSCOPED 지정 된**|**SEGMENT**|**SETIF2**.|

LANGUAGE의 구문은 **language:** <em>x</em>입니다. 여기서 *x* 는 C, SYSCALL, STDCALL, 파스칼, 포트란 또는 BASIC 중 하나입니다.  SYSCALL, 파스칼, 포트란 및 BASIC은에서 사용 되는와 함께 지원 되지 않습니다 [. 모델](../../assembler/masm/dot-model.md) FLAT.

## <a name="see-also"></a>참고 항목

[지시문 참조](directives-reference.md)

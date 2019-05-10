---
title: OPTION (MASM)
ms.date: 08/30/2018
f1_keywords:
- option
helpviewer_keywords:
- OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
ms.openlocfilehash: a8215bf1f816baa490a768fb2cab0b3c2e53e20b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217259"
---
# <a name="option-masm"></a>OPTION (MASM)

있으며 어셈블러의 기능을 사용 하지 않도록 설정 합니다.

## <a name="syntax"></a>구문

> 옵션 *optionlist*

## <a name="remarks"></a>설명

사용 가능한 옵션은 다음과 같습니다.

|||||
|-|-|-|-|
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**EMULATOR**|
|**NOEMULATOR**|**EPILOGUE**|**EXPR16**|**EXPR32**|
|**LANGUAGE**|**LJMP**|**NOLJMP**|**M510**|
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|
|**PROC**|**PROLOGUE**|**READONLY**|**NOREADONLY**|
|**SCOPED**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|

언어에 대 한 구문은 **언어 옵션:**<em>x</em>여기서 *x* C, SYSCALL, STDCALL, PASCAL, FORTRAN, 또는 BASIC 중 하나입니다.  SYSCALL, PASCAL, FORTRAN, 및 BASIC은 지원 되지 않습니다 사용한 [합니다. 모델](../../assembler/masm/dot-model.md) 평면입니다.

## <a name="see-also"></a>참고자료

[지시문 참조](../../assembler/masm/directives-reference.md)<br/>
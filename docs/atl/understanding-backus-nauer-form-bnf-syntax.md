---
title: ATL 등록자 및 Backus Nauer BNF (Form) 구문
ms.date: 11/04/2016
helpviewer_keywords:
- BNF notation
- Backus Nauer Form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
ms.openlocfilehash: 0b48e0b4abc8601b5173c3c7d2748c726646fbc5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196464"
---
# <a name="understanding-backus-nauer-form-bnf-syntax"></a>Backus Nauer BNF (Form) 구문 이해

ATL 등록자 사용 하는 스크립트는 다음 표에 나와 있는 표기법을 사용 하는 BNF 구문을 사용 하 여이 항목에 설명 되어 있습니다.

|규칙/기호|의미|
|------------------------|-------------|
|::=|해당 항목|
|&#124;|또는|
|X+|하나 이상의 Xs 합니다.|
|[X]|X는 선택 사항입니다. 선택적 구분 기호는  \[].|
|모든 **굵은** 텍스트|문자열 리터럴입니다.|
|모든 *기울임꼴* 텍스트|리터럴 문자열을 생성 하는 방법입니다.|

앞의 표에 표시 된 것과 같이 등록자 스크립트 문자열 리터럴을 사용 합니다. 이러한 값은 스크립트에 표시 되어야 하는 실제 텍스트입니다. 다음 표에서 ATL 등록자 스크립트에 사용 되는 문자열 리터럴을 설명 합니다.

|문자열 리터럴|작업|
|--------------------|------------|
|**ForceRemove**|(있는 경우) 다음 키를 완전히 제거 하 고 다시 만듭니다.|
|**NoRemove**|등록 취소 하는 동안 다음 키를 제거 하지 않습니다.|
|**val**|지정 `<Key Name>` 실제로 명명 된 값입니다.|
|**삭제**|등록 하는 동안 다음 키를 삭제합니다.|
|**s**|다음 값을 문자열 (REG_SZ) 임을 지정 합니다.|
|**d**|다음 값을 DWORD (REG_DWORD) 임을 지정 합니다.|
|**m**|다음 값을 문자열 (REG_MULTI_SZ) 임을 지정 합니다.|
|**b**|다음 값을 이진 값 (REG_BINARY) 임을 지정 합니다.|

## <a name="bnf-syntax-examples"></a>BNF 구문 예제

표기법 및 문자열 리터럴에 ATL 등록자 스크립트에서 작동 하는 방법을 이해할 수 있도록 몇 가지 구문 예는 다음과 같습니다.

### <a name="syntax-example-1"></a>구문 예제 1

```
<registry expression> ::= <Add Key>
```

형식임 `registry expression` 같습니다 `Add Key`합니다.

### <a name="syntax-example-2"></a>구문 예제 2

```
<registry expression> ::= <Add Key> | <Delete Key>
```

형식임 `registry expression` 동일 `Add Key` 또는 `Delete Key`합니다.

### <a name="syntax-example-3"></a>구문 예제 3

```
<Key Name> ::= '<AlphaNumeric>+'
```

형식임 `Key Name` 하나 이상의 해당 `AlphaNumerics`합니다.

### <a name="syntax-example-4"></a>구문 예제 4

```
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>
```

지정 `Add Key` 동일 `Key Name`, 및 문자열 리터럴 `ForceRemove`, `NoRemove`, 및 `val`는 선택 사항입니다.

### <a name="syntax-example-5"></a>구문 예제에서는 5

```
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0
```

지정 `AlphaNumeric` 모든 비 NULL 문자에 해당 합니다.

### <a name="syntax-example-6"></a>구문 예제 6

```
val 'testmulti' = m 'String 1\0String 2\0'
```

지정 하는 키 이름을 `testmulti` 다중 값 이루어집니다 `String 1` 및 `String 2`합니다.

### <a name="syntax-example-7"></a>구문 예 7

```
val 'testhex' = d '&H55'
```

지정 하는 키 이름을 `testhex` DWORD 값은 16 진수 55 (10 진수 85)로 설정 합니다. 이 형식을 준수 하는 참고 합니다 **& H** 표기법으로 Visual Basic 사양에서 찾을 수 있습니다.

## <a name="see-also"></a>참고자료

[등록자 스크립트 만들기](../atl/creating-registrar-scripts.md)

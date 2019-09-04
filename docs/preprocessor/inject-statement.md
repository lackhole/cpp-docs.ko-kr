---
title: inject_statement import 특성
ms.date: 08/29/2019
f1_keywords:
- inject_statement
helpviewer_keywords:
- inject_statement attribute
ms.assetid: 07d6f0f4-d9fb-4e18-aa62-f235f142ff5e
ms.openlocfilehash: 25dee621ff8af2c9a39e605b9da2c29d80f9570a
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220998"
---
# <a name="inject_statement-import-attribute"></a>inject_statement import 특성

**C++컴퓨터별**

소스 텍스트로서 인수를 형식 라이브러리 헤더에 삽입합니다.

## <a name="syntax"></a>구문

> **#import** *형식 라이브러리* **inject_statement (** "*원본-텍스트*" **)**

### <a name="parameters"></a>매개 변수

*원본-텍스트*\
형식 라이브러리 헤더 파일에 삽입되는 소스 텍스트입니다.

## <a name="remarks"></a>설명

텍스트는 헤더 파일의 *형식 라이브러리* 콘텐츠를 래핑하는 네임 스페이스 선언의 시작 부분에 배치 됩니다.

**끝 C++ 특정**

## <a name="see-also"></a>참고자료

[#import 특성](../preprocessor/hash-import-attributes-cpp.md)\
[#import 지시문](../preprocessor/hash-import-directive-cpp.md)
